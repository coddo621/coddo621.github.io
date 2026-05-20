<script lang="ts">
    import { onMount } from "svelte"

    type CarouselItem = {
        title: string
        description: string
        image: string
        url: string
    }

    export let items: CarouselItem[] = []

    let current = 0
    let interval: ReturnType<typeof setInterval>

    function next() {
        current = (current + 1) % items.length
    }

    function previous() {
        current = (current - 1 + items.length) % items.length
    }

    function startAutoSlide() {
        clearInterval(interval)
        interval = setInterval(next, 5000)
    }

    function pauseAutoSlide() {
        clearInterval(interval)
    }

    onMount(() => {
        startAutoSlide()

        return () => clearInterval(interval)
    })
</script>

<style>
    .carousel {
        position: relative;
        width: 100%;
        overflow: hidden;
    }

    .track {
        display: flex;
        transition: transform 0.5s ease;
        transform: translateX(calc(-100% * var(--index)));
    }

    .slide {
        min-width: 100%;
        display: flex;
        justify-content: center;

        padding: 1rem;
        box-sizing: border-box;
    }

    .controls {
        position: absolute;
        inset: 50% 0 auto 0;

        transform: translateY(-50%);

        display: flex;
        justify-content: space-between;

        padding-inline: 1rem;

        pointer-events: none;
    }

    .button {
        width: 3.5rem;
        height: 3.5rem;

        border: none;
        border-radius: 9999px;

        background-color: #381d2a;
        color: white;

        font-size: 1.5rem;

        cursor: pointer;

        display: flex;
        align-items: center;
        justify-content: center;

        transition:
            transform 0.2s ease,
            background-color 0.2s ease;

        pointer-events: all;
    }

    .button:hover {
        background-color: rgba(56, 29, 42, 0.9);
        transform: scale(1.05);
    }

    .dots {
        display: flex;
        justify-content: center;
        gap: 0.75rem;

        margin-top: 1.5rem;
    }

    .dot {
        width: 0.75rem;
        height: 0.75rem;

        border-radius: 9999px;

        background-color: rgba(255, 165, 82, 0.4);

        transition:
            transform 0.2s ease,
            background-color 0.2s ease;
    }

    .dot.active {
        background-color: #ffa552;
        transform: scale(1.2);
    }

    @media (max-width: 48rem) {
        .button {
            width: 3rem;
            height: 3rem;

            font-size: 1.25rem;
        }

        .controls {
            padding-inline: 0.5rem;
        }
    }
</style>

<div
    class="carousel"
    role="region"
    on:mouseenter={pauseAutoSlide}
    on:mouseleave={startAutoSlide}
>
    <div
        class="track"
        style={`--index: ${current}`}
    >
        {#each items as item}
            <div class="slide">
                <slot {item} />
            </div>
        {/each}
    </div>

    <div class="controls">
        <button
            class="button"
            on:click={previous}
            aria-label="Previous"
        >
            ←
        </button>

        <button
            class="button"
            on:click={next}
            aria-label="Next"
        >
            →
        </button>
    </div>
</div>

<div class="dots">
    {#each items as _, index}
        <div
            class="dot"
            class:active={index === current}
        ></div>
    {/each}
</div>