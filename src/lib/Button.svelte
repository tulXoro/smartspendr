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
        font-size: 26px;
        margin: auto;
        display: flex; 
        width: auto;
        height: auto;
    }
    .primary{
        background: #d91b42;
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
       color: #d91b42;
    }

    a{
        text-decoration: none;
    }
</style>