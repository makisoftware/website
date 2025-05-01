<script>
    import Project from "$lib/Project.svelte";
    import { IMESSAGE_LINK } from "../../constants";
</script>

<svelte:head>
    <title>Projects • Maki Software</title>
</svelte:head>

<div class="level-two-container">
    <div class="level-two-text-area">
        <h1>Projects</h1>
        <Project link={IMESSAGE_LINK} imagePath="/new.jpeg" title="New" description="Launching soon, join the iMessage group to stay tuned" />
        <Project link="https://t4t.social" imagePath="/t4t.png" title="t4t" description="Community for trans and gender-non-comforming people" />
        <Project link="https://pingpractice.org/" imagePath="/practice.png" title="Ping Practice" description="Miniature bits of mindfulness" />
        <Project link="https://dwelling.love/" imagePath="/dwelling.png" title="Dwelling" description="A social network for your home" />
    </div>
</div>