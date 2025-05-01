<script lang="ts">
  import { base } from "$app/paths";

  export let home: boolean;
</script>

<div class="nav-container" style="width: {home ? 440 : 820}px; height: {home ? 440 : 780}px">
  {#if home}
    <a href="{base}/contact">Contact</a>
    <a href="{base}/projects">Projects</a>
  {:else}
    <a href="/">Home</a>
  {/if}
</div>

<style>
  .nav-container {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    justify-content: space-between;
    align-items: center;
    pointer-events: none;
  }

  a {
    margin: 0;
    padding: 0;
    color: white;
    text-decoration: none;
    font-size: 1.2em;
    transition: opacity 0.3s ease;
    text-align: center;
    pointer-events: auto;
  }

  a:hover {
    opacity: 0.7;
  }

  @media (max-width: 640px) {
    .nav-container {
      flex-direction: column;
    }
  }
</style>
