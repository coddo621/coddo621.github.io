<script lang="ts">
    import { Navbar, Hero, Gallery, Projects } from '$lib';    
</script>

<style>
    :global(h1) {
        text-align: center;
        font-size: 20vh;
        color: #fed681;
        line-height: 0.8;
        margin: 0;
    }

    :global(h2) {
        font-size: 15vh;
        text-align: center;
        color: #ba5624;
    }

    :global(h3) {
        font-size: 5vh;
    }

    :global(h4) {
        font-size: 2.5vh;
    }

    :global(a) {
        color: #ba5624;
        text-decoration-line: underline;
    }

    :global(p) {
        font-size: 2.5vh;
        color: #000000;
    }

    :global(li) {
        font-size: 2.5vh;
        list-style-type: disc;
    }
</style>

<Navbar></Navbar>
<Hero></Hero>
<Projects></Projects>
<Gallery></Gallery>