<script>
    export let typeOf = 'primary'
    export let url = '/'
</script>

<a href={url}>
    <button class={typeOf} type="submit">
        <slot></slot> 
    </button>
</a>


<style>
    button{
        border: 0;
        cursor: pointer;
        border-radius: 6px;
        padding: 8px 12px;
        font-weight: bold;
        box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
        font-size: 1.5rem;
        margin: auto;
        display: flex; 
        width: auto;
        height: auto;
    }
    .primary{
        background: #2563EB;
        color: white;
        align-items: center; 
        justify-content: center; 
        width: 25vw;
    }
    .signup{
       border: none;
       background: none;
       box-shadow: none;
       font-weight: 500;
       color: #2563EB;
       font-size: 1.3rem;
    }

    a{
        text-decoration: none;
    }
</style>