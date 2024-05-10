<script>
    import "../app.css";
    import { onMount } from "svelte";
    import NavBar from "../lib/NavBar.svelte";
</script>

<style>
  .page-content {
    padding-bottom: 400px; /* Adjust this value based on the height of your navbar */
  }
</style>

<NavBar/>

<div class="page-content">
  <slot />
</div>