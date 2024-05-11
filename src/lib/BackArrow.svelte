<script>
    import backArrow from '$lib/backArrow.png';
    export let typeOf = 'icon'
</script>

<style>
    img {
        height: auto;
        width: 4vw;
    }
    a {
        width: 4vw;
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
