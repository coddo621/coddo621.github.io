<script lang="ts">
    export let title: string
    export let description: string
    export let image: string
    export let url: string
</script>

<style>
    .card {
        width: min(100%, 50rem);
        min-height: 42rem;

        background-color: #ffa552;
        border-radius: 1.5rem;

        padding: 2rem;

        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1.5rem;

        text-align: center;
        box-sizing: border-box;
    }

    .image-wrapper {
        width: 100%;
        height: clamp(16rem, 40vw, 24rem);

        display: flex;
        align-items: center;
        justify-content: center;

        overflow: hidden;
    }

    .card img {
        height: 100%;
        width: auto;

        object-fit: contain;

        display: block;
        border-radius: 1rem;
    }

    .card h3,
    .card h4 {
        color: #fcde9c;
        margin: 0;
    }

    .card h3 {
        font-size: clamp(1.5rem, 3vw, 2.25rem);
    }

    .card h4 {
        font-size: clamp(1rem, 2vw, 1.25rem);
        line-height: 1.5;
        font-weight: 500;
    }

    .card a {
        text-decoration: none;
        color: inherit;
    }

    @media (max-width: 48rem) {
        .card {
            min-height: auto;
            padding: 1.5rem;
        }

        .image-wrapper {
            height: clamp(14rem, 50vw, 18rem);
        }
    }
</style>

<div class="card">
    <a href={url} target="_blank" class="image-wrapper">
        <img src={image} alt={title} />
    </a>

    <h3>{title}</h3>
    <h4>{description}</h4>
</div>