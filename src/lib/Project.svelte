<script lang="ts">
  import { base } from '$app/paths';

  export let imagePath: string;
  export let title: string;
  export let description: string;
  export let link: string;

  $: isExternal = /^https?:\/\//i.test(link);
  $: normalizedInternalPath = link.startsWith('/') ? link : '/' + link;
  $: href = isExternal ? link : base + normalizedInternalPath;
</script>

<div class="project-container">
  <img src={imagePath} alt={title} />
  <div class="text-container">
    <a href={href} class="underlined">{title}</a>
    <p>{description}</p>
  </div>
</div>

<style>
  .project-container {
    display: flex;
    gap: 1rem;
    margin-bottom: 2rem;
  }

  img {
    width: 54px;
    height: 54px;
    border-radius: 12px;
    object-fit: cover;
    align-self: flex-start;
  }

  .text-container {
    flex: 1;
  }

  a {
    font-family: 'Inter', sans-serif;
  }

  p {
    margin: 0;
    padding: 0;
  }

</style>
