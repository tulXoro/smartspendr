<script>
    export let addExpense;
    export let close;

    let description = '';
    let amount = '';
    let category = '';

    function submit() {
        if (description && amount > 0 && category) {
            addExpense({ description, amount, category, percentage: 0, color: '#34495e' });
            close();
        } else {
            alert('Please fill in all fields correctly.');
        }
    }
</script>

<div class="modal">
    <h2 style="color:#2c3e50">Add New Expense</h2>
    <div class="input-group">
        <label for="description">Description</label>
        <input id="description" type="text" bind:value={description} placeholder="Enter description">
    </div>
    <div class="input-group">
        <label for="amount">Amount</label>
        <input id="amount" type="number" bind:value={amount} placeholder="Enter amount">
    </div>
    <div class="input-group">
        <label for="category">Category</label>
        <input id="category" type="text" bind:value={category} placeholder="Enter category">
    </div>
    <button class="submit-btn" on:click={submit}>Submit</button>
    <button class="close-btn" on:click={close} style="color: white; font-weight: bold;">Close</button>
</div>

<style>
    .modal {
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        background-color: #ecf0f1;
        padding: 20px;
        border-radius: 8px;
        width: 300px;
        box-shadow: 0 4px 16px rgba(0,0,0,0.2);
        z-index: 10;
    }
    .input-group {
        margin-bottom: 15px;
    }
    input {
        width: 100%;
        padding: 8px;
        margin-top: 5px;
        border-radius: 4px;
        border: 1px solid #ccc;
        box-sizing: border-box;
    }
    label {
        display: block;
        margin-bottom: 5px;
        color: #2c3e50;
    }
    .submit-btn, .close-btn {
        padding: 10px 20px;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        margin-top: 10px;
        width: 100%;
    }
    .submit-btn {
        background-color: #2563EB;
        color: white;
    }
    .close-btn {
        background-color: #E53E3E;
        color: white;
        margin-top: 5px;
    }
</style>