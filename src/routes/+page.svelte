<script>
	import Button from "../lib/Button.svelte";

</script>

<svelte:head>
	<title>Welcome</title>
	<meta name="description" content="Welcome Page" />
</svelte:head>

<style>
    h3{
        margin-bottom: 0;
        padding: 0;
        font-weight: 300;
        font-size: 2.5rem;
    }
    h1{
        margin-top: 0;
        margin-bottom: 50px;
        padding: 0;
        font-size: 4rem;
    }
    .welcomeSign{
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .outer {
        height: 100vh; 
        display: flex;
        flex-direction: column;
        justify-content: center; 
    }
    .page-container {
        height: 100vh; 
    }
</style>

<div class="page-container">
    <div class="outer">
        <div class="welcomeSign">
            <h3>WELCOME TO</h3>
            <h1>SmartSpendr</h1>
        </div>
        <Button typeOf="primary" url='login'>Log In</Button>
        <Button typeOf="signup" url='/register'>Sign Up</Button>
    </div>
</div>