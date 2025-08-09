<script lang="ts">
  import { base } from "$app/paths";
  import { page } from "$app/stores";

  $: path = $page.url.pathname;
  $: segments = path.split('/').filter(Boolean);
  $: depth = segments.length === 0 ? 1 : 1 + segments.length; // 1: home, 2: /contact or /projects, 3+: deeper
  $: isHome = depth === 1;
  $: parentPath = isHome ? '/' : '/' + segments.slice(0, -1).join('/');

  function titleCaseFromSegment(segment: string): string {
    return segment
      .split('-')
      .map((word) => word.charAt(0).toUpperCase() + word.slice(1))
      .join(' ');
  }

  $: parentLabel = parentPath === '/' ? 'Home' : titleCaseFromSegment(parentPath.split('/').filter(Boolean).slice(-1)[0] ?? '');

  $: navWidthPx = depth === 1 ? 504 : depth === 2 ? 884 : 1292;
</script>

<div class="nav-container" style={`width: ${navWidthPx}px;`}>
  {#if isHome}
    <a href={base + '/contact'}>Contact</a>
    <a href={base + '/projects'}>Projects</a>
  {:else if depth === 2}
    <a class="home-link" href={base + '/'}>Home</a>
  {:else}
    <a class="back-link" href={base + parentPath}>{parentLabel}</a>
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
</style>
