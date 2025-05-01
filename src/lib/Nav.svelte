<script lang="ts">
  import { base } from "$app/paths";

  export let home: boolean;
</script>

<div class="nav-container" style="width: {home ? 504 : 884}px; height: {home ? 504 : 684}px">
  {#if home}
    <a href="{base}/contact">Contact</a>
    <a href="{base}/projects">Projects</a>
  {:else}
    <a class="home-link" href="/">Home</a>
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
    pointer-events: auto;
    margin: 0;
    padding: 2rem;
    color: white;
    text-decoration: none;
    font-size: 1.2em;
    transition: opacity 0.3s ease;
    text-align: center;
  }

  a:hover {
    opacity: 0.7;
  }

  @media (max-width: 820px) {
    .nav-container {
      flex-direction: column;
    }
  }
</style>
