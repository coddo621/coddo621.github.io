<script lang="ts">
    import Carousel from "./ui/Carousel.svelte"
    import Card from "./ui/Card.svelte"

    import shape from "$lib/assets/shape.png"
    import mpp from "$lib/assets/mpp.png"
    import dg from "$lib/assets/dg.png"

    const projects = [
        {
            title: "Shape",
            description:
                "A Google Forms-like web application for creating and sharing surveys",
            image: shape,
            url: "https://github.com/coddo621/Shape",
        },

        {
            title: "MusicPlayerPy",
            description:
                "Small Python project; Music player made using pygame and ctk",
            image: mpp,
            url: "https://github.com/coddo621/MusicPlayerPy",
        },

        {
            title: "Dionysus Games",
            description:
                "Indie game development studio I co funded with DOminikRogic",
            image: dg,
            url: "https://github.com/Dionysus-Games",
        },
    ]
</script>

<style>
    .projects {
        width: 100%;
        max-width: 80rem;

        margin-inline: auto;

        padding: 4rem 1.5rem;

        display: flex;
        flex-direction: column;
        gap: 2rem;
    }

    @media (max-width: 48rem) {
        .projects {
            padding: 3rem 1rem;
        }
    }
</style>

<div class="projects" id="projects">
    <h2>Projects</h2>

    <Carousel items={projects} let:item>
        <Card
            title={item.title}
            description={item.description}
            image={item.image}
            url={item.url}
        />
    </Carousel>
</div>