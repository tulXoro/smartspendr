<script>
    import "../app.css";
    import { onMount } from "svelte";
    import NavBar from "../components/NavBar.svelte";
    import Footer from "../components/Footer.svelte";
    let isNavOpen = false;

    onMount(() => {
    const handleResize = () => {
        if (window.innerWidth > 768) {
        isNavOpen = true;
        } else {
        isNavOpen = false;
        }
    };

    window.addEventListener("resize", handleResize);
    handleResize();

    return () => {
        window.removeEventListener("resize", handleResize);
    };
    });
</script>

<button class="md:hidden" on:click={() => (isNavOpen = !isNavOpen)}>
    Toggle Menu
</button>

<div class={`navbar ${isNavOpen ? "" : "hidden"} md:block`}>
    <NavBar />
</div>



<slot />
<Footer/>