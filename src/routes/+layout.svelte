<script>
    import "../app.css";
    import { onMount } from "svelte";
    import NavBar from "../lib/NavBar.svelte";
    import { session } from "../store/sessionStore";
</script>

<style>
  .page-content {
    padding-bottom: 400px; /* Adjust this value based on the height of your navbar */
  }
</style>

{#if $session.isLoggedIn}
  <NavBar/>
{/if}

<div class="page-content">
  <slot />
</div>