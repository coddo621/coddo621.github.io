<script>
    import hero from "$lib/assets/hero.png"
    import github from "$lib/assets/github.svg"
    import bsky from "$lib/assets/bsky.svg"
    import steam from "$lib/assets/steam.svg"

    const riteh_url = "https://riteh.uniri.hr/en/"
    const github_url = "https://github.com/coddo621"
    const bsky_url = "https://bsky.app/profile/coddo.furryplace.eu"
    const steam_url = "https://steamcommunity.com/id/coddo621"
</script>

<style>
    .hero {
        display: flex;
        align-items: flex-start;
        justify-content: space-between;
        gap: 2rem;

        width: 100%;
        max-width: 1400px;
        margin: auto;
        padding: 2rem;

        box-sizing: border-box;
    }

    .hero-content {
        width: 70%;
        min-width: 0;
    }

    .hero-header {
        background-color: #ffa552;
        border-radius: 1rem;

        width: 100%;
        box-sizing: border-box;

        margin-bottom: 2rem;
        padding: 1.5rem 2rem;
    }

    .hero-header h1 {
        margin: 0 0 1rem 0;
        -webkit-text-stroke: 2px black;
    }

    .hero-links {
        display: flex;
        flex-direction: row;
        justify-content: center;
        gap: 1rem;
    }

    .hero-links img {
        width: 40px;
        height: 40px;
        object-fit: contain;

        transition: transform 0.2s ease;
    }

    .hero-links img:hover {
        transform: scale(1.1);
    }

    .hero-about {
        width: 100%;
        box-sizing: border-box;
    }

    .hero-image-wrapper {
        width: 30%;
        display: flex;
        justify-content: flex-end;
    }

    .hero-image {
        width: 100%;
        max-width: 400px;
        height: auto;

        object-fit: contain;
        display: block;
    }

    @media (max-width: 900px) {
        .hero {
            flex-direction: column;
            align-items: center;
        }

        .hero-content,
        .hero-image-wrapper {
            width: 100%;
        }

        .hero-image-wrapper {
            justify-content: center;
        }

        .hero-image {
            max-width: 350px;
        }
    }

    @media (max-width: 600px) {
        .hero {
            padding: 1rem;
        }

        .hero-header {
            padding: 1rem;
        }

        .hero-links img {
            width: 32px;
            height: 32px;
        }

        .hero-image {
            max-width: 280px;
        }
    }
</style>

<div class="hero" id="hero">
    <div class="hero-content">
        <div class="hero-header">
            <h1>Coddo</h1>

            <div class="hero-links">
                <a href={github_url} target="_blank">
                    <img src={github} alt="github">
                </a>

                <a href={bsky_url} target="_blank">
                    <img src={bsky} alt="bluesky">
                </a>

                <a href={steam_url} target="_blank">
                    <img src={steam} alt="steam">
                </a>
            </div>
        </div>

        <div class="hero-about">
            <h3>
                Computer science undergrad @
                <a href={riteh_url} target="_blank">RiTEh</a>
            </h3>

            <p>
                Hi, I'm Coddo, a 21 year old Computer Science student at
                The Faculty of Engineering in Rijeka, Croatia currently
                working on my undergraduate degree.
                <br><br>

                I work part time as an aspiring web designer and developer
                and focus my work on more modern and useful frameworks.
                <br><br>

                Outside of my studies and work I spend my time on:
            </p>

            <ul>
                <li>Guitar</li>
                <li>Gaming</li>
                <li>Music</li>
                <li>Self Hosting</li>
            </ul>
        </div>
    </div>

    <div class="hero-image-wrapper">
        <img class="hero-image" src={hero} alt="hero.jpg">
    </div>
</div>