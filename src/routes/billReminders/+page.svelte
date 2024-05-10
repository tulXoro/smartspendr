<script>
    let showModal = false;
    let billName = "";
    let cost = "";
    let recurrence = "";

    /**
	 * @type {string | any[]}
	 */
    let billItems = [[]];

    function toggleModal() {
        showModal = !showModal;
    }

    function add(){
        if (billName != "" && cost != "" && recurrence != ""){
            let newBill = [billName, cost, recurrence];
            billItems = [...billItems, newBill];
        }

        showModal = !showModal;

        billName = "";
        cost = "";
        recurrence = "";
    }
</script>

<svelte:head>
	<title>Bill Reminders</title>
	<meta name="description" content="Bill Reminders Page" />
</svelte:head>

<style>
	h1{
		font-size: 3rem;
	}
	.container{
		display: flex;
		flex-direction: column;
		align-items: start;
	}
    .background {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100vw;
        height: 100vh;
        position: fixed;
        background: rgba(169, 169, 169, 0.9);
        left: 0;
        right: 0;
    }
    .modal {
        width: 450px;
        height: 500px;
        border-radius: 10px;
        background-color: white;
    }
    .billButton{
        border: 0;
        cursor: pointer;
        border-radius: 30px;
        font-weight: bold;
        box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
        font-size: 2vw;
        margin: 30px;
        display: flex; 
        background: #d91b42;
        color: white;
        align-items: center; 
        justify-content: center; 
        width: 10vw;
        height: 7vh;
    }
    .cancel{
        border-color: #d91b42;
        cursor: pointer;
        border-radius: 6px;
        padding: 8px 12px;
        font-size: 26px;
        height: auto;
        color: #d91b42;
        background-color: white;
        width: 100px;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 5px;
    }
    .save{
        border-color: #d91b42;
        cursor: pointer;
        border-radius: 6px;
        padding: 8px 12px;
        font-size: 26px;
        height: auto;
        color: white;
        background-color: #d91b42;
        width: 100px;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 5px;
    }
    .modalh1 {
        margin: 15px 0px 80px 20px;
        font-size: 40px;
        font-weight: 500;
    }
    form {
        position: relative;
        bottom: 70px;
        display: flex;
        flex-direction: column;
    }
    label {
        font-weight: bold;
        margin: 15px 20px 0px;
    }
    input {
        margin: auto;
        margin-top: 5px;
        height: 5vh;
        width: 90%;
        background: rgba(231, 231, 231);
        border: 0;
        border-radius: 3px;
        padding: 5px;
    }
    input::placeholder {
        font-weight: bold;
        padding: 5px;
    }
    .modalButtons {
        display: flex;
        justify-content: center;
        position: relative;
        bottom: 30px;
    }
    ul {
        width: 80%;
        height: auto;
        margin: auto;
        padding: 5px;
    }
    li {
        list-style: none;
        display: flex;
        flex-direction: row;
        font-weight: 500;
        box-shadow: 2px 2px 8px 4px rgba(0, 0, 0, 0.2);
        font-size: 1rem;
        height: 15vh;
        align-items: start;
        flex-wrap: wrap;
        border-radius: 6px;
        justify-content: space-between;
        margin: auto;
        margin-bottom: 15px;
    }
    .heading {
        display: flex;
        flex-direction: row;
        align-items: center;
        margin-top: 6vh;
        margin-left: 5vw;
    }
    .emptyContainer {
        background-color: rgba(217, 27, 66, 0.2);
        width: 90%;
        height: 50vh;
        border-radius: 15px;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
        margin: auto;
    }
    h2 {
        color: #d91b42;
    }
    .type {
        color: black;
        margin-left: 20px;
        margin-right: 10px;
        margin-top: 10px;
        font-size: 1.5rem;
    }
    .recurrence {
        margin-left: 20px;
        margin-top: -40px;
        color: gray;
    }
    .break {
        flex-basis: 100%;
        height: 0;
    }
</style>

{#if showModal}
<div class="background">
    <div class="modal">
        <h1 class="modalh1">Add New Bill</h1>
        <form>
            <label for="billName">Name of Bill</label>
            <input id="billName" class="input" type="text" placeholder="Enter Name of Bill" bind:value={billName}>
            <label for="cost">Cost</label>
            <input id="cost" class="input" type="text" placeholder="Enter Cost of Bill" bind:value={cost}>
            <label for="recurrence">Recurrence</label>
            <input id="recurrence" class="input" type="text" placeholder="Enter Recurrence of Bill" bind:value={recurrence}>
        </form>
        <div class="modalButtons">
            <button class="cancel" on:click={toggleModal}>Cancel</button>
            <button class="save" on:click={add}>Save</button>
        </div>
    </div>
</div>
{/if}

<div>
	<div class="container">
        <div class="heading">
            <h1>My Bill Reminders</h1>
            <button class="billButton" on:click={toggleModal}>+Add</button>
        </div>
        {#if billItems.length > 1}
        <ul>
            {#each billItems.slice(1) as [first, second, third]}
                <li>
                    <h2 class="type">{first} - ${second}</h2>
                    <div class="break"></div>
                    <p class="recurrence">{third}</p>
                </li>
            {/each}
        </ul>
        {:else}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <!-- svelte-ignore a11y-no-static-element-interactions -->
        <div class="emptyContainer" on:click={toggleModal}>
            <h2>
                +Add Bill Reminder
            </h2>
        </div>
        {/if}
    </div>   
</div>