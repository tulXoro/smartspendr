<script>
	import Button from '../../lib/Button.svelte';
 import { session } from "../../store/sessionStore";

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
		font-size: 2.5rem;
		text-align: center;
	}
	h1{
		margin-top: 0;
		font-size: 4rem;
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
        width: 90%;
        height: 8vh;
        padding: 12px;
        margin: auto;
		margin-bottom: 10px;
        border: 1px solid #ccc;
        border-radius: 4px;
        box-sizing: border-box;
    }
    .outer {
        margin: 10vh;
    }
</style>

<div class="outer">
	<div class="welcomeSign">
		<h3>WELCOME BACK TO</h3> 
		<h1>SmartSpendr</h1>
	</div>   
	<form class="form" on:submit={()=>{session.set({isLoggedIn: true})}} >
        <input class="input" type="text" placeholder="Enter Username" bind:value={username}>
		<input class="input" type="text" placeholder="Enter Password" bind:value={password}>

<Button type="submit" typeOf="primary" url='/transaction'>Log In</Button>
	</form>
	
	<Button typeOf="signup" url='/register'>Sign Up</Button>
</div>