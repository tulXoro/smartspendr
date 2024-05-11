<script>
    import backArrow from '$lib/backArrow.png';
    export let typeOf = 'icon'
</script>

<style>
    img {
        height: auto;
        width: 10vw;
    }
    a {
        width: 10vw;
        display: flex;
        margin-top: 20px;
    }
    .moved {
        margin-left: 60px;
    }
</style>

<a href="/profile" class={typeOf}>
    <img src={backArrow} alt="back arrow" />
</a>
