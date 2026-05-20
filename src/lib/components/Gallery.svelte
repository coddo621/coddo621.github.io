<script lang="ts">
    import GalleryComp from "./ui/GalleryComp.svelte"
    import hoodie from "$lib/assets/comms/hoodie.jpg"
    import chibi from "$lib/assets/comms/chibi.jpg"
    import shirt from "$lib/assets/comms/shirt.jpg"
    import reff from "$lib/assets/comms/reff.png"
    import couple from "$lib/assets/comms/couple.png"
    import loser from "$lib/assets/comms/loser.png"
    import dumbass from "$lib/assets/comms/dumbass.jpg"

    let GalleryImage = [
        {
            src: hoodie,
            width: 1166,
            height: 1917
        },
        {
            src: chibi,
            width: 801,
            height: 978
        },
        {
            src: shirt,
            width: 590,
            height: 1024
        },
        {
            src: reff,
            width: 1268,
            height: 972
        },
        {
            src: couple,
            width: 1268,
            height: 900
        },
        {
            src: loser,
            width: 1000,
            height: 1000
        },
        {
            src: dumbass,
            width: 868,
            height: 582
        }
    ]
</script>

<div id="gallery">
    <h2>Gallery</h2>
    <GalleryComp images={GalleryImage}></GalleryComp>
</div>