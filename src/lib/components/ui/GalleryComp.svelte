<script lang="ts">
	type GalleryImage = {
		src: string;
		width: number;
		height: number;
	};

	type PositionedImage = GalleryImage & {
		column: number;
	};

	export let images: GalleryImage[] = [];

	export let gap: number = 12;
	export let maxColumns: number = 5;

	let containerWidth = 1200;

	function getColumns(width: number): number {
		if (width < 500) return 2;
		if (width < 800) return 3;
		if (width < 1100) return 4;
		return maxColumns;
	}

	$: activeColumns = getColumns(containerWidth);

	$: positioned = (() => {
		const heights = Array(activeColumns).fill(0);
		const result: PositionedImage[] = [];

		for (const img of images) {
			const aspect = img.height / img.width;

			let bestCol = 0;
			let minHeight = heights[0];

			for (let i = 1; i < activeColumns; i++) {
				if (heights[i] < minHeight) {
					minHeight = heights[i];
					bestCol = i;
				}
			}

			heights[bestCol] += aspect;
			result.push({ ...img, column: bestCol });
		}

		return result;
	})();

	function resizeObserver(node: HTMLElement): { destroy: () => void } {
		const ro = new ResizeObserver((entries: ResizeObserverEntry[]) => {
			for (const e of entries) {
				containerWidth = e.contentRect.width;
			}
		});

		ro.observe(node);

		return {
			destroy() {
				ro.disconnect();
			}
		};
	}
</script>

<div
	use:resizeObserver
	style="
		width:100%;
		display:grid;
		grid-template-columns: repeat({activeColumns}, 1fr);
		gap:{gap}px;
	"
>
	{#each Array(activeColumns) as _, col}
		<div style="display:flex; flex-direction:column; gap:{gap}px;">
			{#each positioned.filter((p) => p.column === col) as image}
				<div
					style="
						width:100%;
						border-radius:14px;
						overflow:hidden;
						background:#111;
					"
				>
					<img
						src={image.src}
						alt=""
						loading="lazy"
						style="
							width:100%;
							height:auto;
							display:block;
							object-fit:cover;
							transition:transform .25s ease;
						"
						on:mouseenter={(e: MouseEvent) =>
							((e.currentTarget as HTMLImageElement).style.transform =
								'scale(1.03)')}
						on:mouseleave={(e: MouseEvent) =>
							((e.currentTarget as HTMLImageElement).style.transform =
								'scale(1)')}
					/>
				</div>
			{/each}
		</div>
	{/each}
</div>