<script lang="ts">
  export let width: number;
</script>

<div class="nav-container" style="width: {width}px">
  <a href="/contact">
    Contact
  </a>
  <a href="/projects">
    Projects
  </a>
</div>

<style>
  .nav-container {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 1;
  }

  a {
    margin: 0;
    padding: 0;
    color: white;
    text-decoration: none;
    font-size: 1.2em;
    color: white;
    text-decoration: none;
    transition: opacity 0.3s ease;
    text-align: center;
  }

  a:hover {
    opacity: 0.7;
  }

  @media (max-width: 888px) {
    /* .back-link {
        left: 50%;
        transform: translateX(-50%);
    } */

    a {
        top: calc(50% - 400px);
    }
 
    /* .projects .link,
    .contact .link {
        color: white;
    } */
}
</style>
