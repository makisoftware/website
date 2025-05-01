<script lang="ts">
  import '../app.css';
  import Nav from '$lib/Nav.svelte';
  import { page } from '$app/stores';
</script>

<div class={$page.url.pathname === '/' ? 'gradient home' : 'gradient'}>
  <Nav width={400} />
  <slot />
</div>

<style>
  @property --inner-white-stop {
    syntax: '<length>';
    inherits: false;
    initial-value: 180px;
  }

  @property --purple-stop {
    syntax: '<length>';
    inherits: false;
    initial-value: 400px;
  }

  @property --outer-white-stop {
    syntax: '<length>';
    inherits: false;
    initial-value: 800px;
  }

  .gradient {
    display: flex;
    align-items: center;
    justify-content: center;  
    height: 100%;
    width: 100%;
    background: radial-gradient(
      circle at center,
      white,
      white var(--inner-white-stop),
      purple var(--purple-stop),
      white var(--outer-white-stop),
      white
    );
    transition:
      --inner-white-stop 0.2s ease-in-out,
      --purple-stop 0.2s ease-in-out,
      --outer-white-stop 0.2s ease-in-out;
  }

  .home {
    --inner-white-stop: 0px;
    --purple-stop: 200px;
    --outer-white-stop: 400px;
  }
</style>