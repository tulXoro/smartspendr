<script>
    // @ts-nocheck
        import Button from '../../lib/Button.svelte';
    
        let uploaded = false;
        let budget = "";
        let expense = "";
        let cost = "";
    
        /**
         * @type {string | any[]}
         */
        let expenseItems = [[]];
    
        /**
         * @param {{ target: { reset: () => void; }; }} event
         */
        function add(event){
            if(expense != "" && cost != ""){
                let pair = [expense, cost]
                expenseItems = [...expenseItems, pair];
            }
            
            event.target.reset();
        }
    
        let flag = false;
        function saved(event){
            flag = true;
        }
    </script>
    
    <style>
        .button{
            cursor: pointer;
            border-radius: 6px;
            padding: 8px;
            font-weight: bold;
            box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
            font-size: 1rem;
            margin: auto;
            display: flex; 
            height: 5vh;
            background: rgb(223, 139, 153);
            color: white;
            align-items: center; 
            justify-content: center; 
            width: 15vw;
        }
        .form{
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 30px;
            margin-top: 5vh;
        }
        .input{
            width: 100%;
            height: 6vh;
            padding: 12px;
            margin: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }
        .div{
            display: flex;
            flex-direction: row;
            width: 100%;
        }
        ul {
            width: 100%;
            height: auto;
            margin: 10px;
            padding: 5px;
        }
        li {
            list-style: none;
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            padding: 15px;
            box-shadow: 2px 2px 8px 4px rgba(0, 0, 0, 0.2);
            font-size: 1.3rem;
            height: 8vh;
            font-weight: 500;
            margin-bottom: 20px;
            border-radius: 6px;
        }
        .type {
            margin-left: 30px;
        }
        .cost{
            margin-right: 30px;
        }
        label {
            font-size: 2em;
            font-weight: bold;
        }
        h1 {
            display: flex;
            justify-content: center;
            font-size: 3vw;
            margin-top: 20px;
            font-weight: 500;
        }
    </style>
    
    <div>
        <h1>Manage Your Profile</h1>
        <form class="form" on:submit={add}>
            <label for="expense">Add Your Expenses</label>
            <div class="div">
                <input class="input" type="text" placeholder="Expenses" bind:value={expense}>
                <input class="input" type="text" placeholder="Expense Cost" bind:value={cost}>
                <button class="button" type="submit">Add</button>
            </div>  
            {#if expenseItems.length > 1}
            <ul>
                {#each expenseItems.slice(1) as [first, second]}
                    <li>
                        <p class="type">{first}</p>
                        <p class="cost">${second}</p>
                    </li>
                {/each}
            </ul>
            {/if}
        </form>
        
        <form class="form" on:submit={saved}>
            <label for="budget">Add Your Budget</label>
            <div class="div">
                <input class="input" type="text" id="budget" placeholder="Budget" bind:value={budget}>
                {#if flag}
                    <button class="button" type="submit">Saved!</button>
                {:else}
                    <button class="button" type="submit">Add</button>
                {/if}
            </div>
        </form>
        
        <Button typeof="primary" url="/account">Save Profile</Button>
    </div>