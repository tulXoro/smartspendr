
<script>
    export let expenses = [];
    expenses = expenses.map(expense => ({ ...expense, expanded: false })); // 
</script>

<style>
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      gap: 16px;
    }
  
    .card {
  border: 1px solid;
  border-radius: 8px;
  padding: 16px;
  box-shadow: 0 2px 5px;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
  background: none; 
  cursor: pointer; 
  outline: none; 
  width: 100%; 
  text-align: left; 
}
  
    .card-title {
      font-size: 1.25em;
      margin-bottom: 8px;
    }
  
    .card-amount {
      color: #333;
      font-size: 1em;
    }

    .card-details {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.3s ease;
    }

    .card.expanded .card-details {
      max-height: 100px; 
    }
</style>

<div class="grid">
    {#each expenses as expense (expense.id)}
      <button type="button" class="card" style="border-color: {expense.color}; box-shadow: 0 2px 5px {expense.color};" on:click={() => expense.expanded = !expense.expanded} class:expanded={expense.expanded}>
        <div class="card-title">{expense.name}</div>
        <div class="card-amount">${expense.amount}</div>
        <div class="card-details">
          <h1>{expense.details.detail1}</h1> <!-- Display the first detail here -->
          <h1>{expense.details.detail2}</h1> <!-- Display the second detail here -->
        </div>
      </button>
    {/each}
</div>