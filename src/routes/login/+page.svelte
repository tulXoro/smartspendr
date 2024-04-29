<script>
	import Button from '../../lib/Button.svelte';

	let username = "";
	let password = "";

</script>

<svelte:head>
	<title>Welcome</title>
	<meta name="description" content="Log Into Account" />
</svelte:head>

<style>
	h3{
		margin-bottom: 0;
		padding: 0;
		font-weight: 300;
		font-size: 3rem;
	}
	h1{
		margin-top: 0;
		font-size: 5rem;
	}
	.welcomeSign{
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.form{
        display: flex;
        flex-direction: column;
        padding: 30px;
    }
    .input{
        width: 100%;
        height: 8vh;
        padding: 12px;
        margin: 8px;
        border: 1px solid #ccc;
        border-radius: 4px;
        box-sizing: border-box;
    }
    .outer {
        margin-top: 20vh;
    }
</style>

<div class="outer">
	<div class="welcomeSign">
		<h3>WELCOME TO</h3> 
		<h1>SmartSpendr</h1>
	</div>   
	<form class="form">
        <input class="input" type="text" placeholder="Enter Username" bind:value={username}>
		<input class="input" type="text" placeholder="Enter Password" bind:value={password}>
	</form>
	<Button typeOf="primary">Log In</Button>
	<Button typeOf="signup" url='/register'>Sign Up</Button>
</div>