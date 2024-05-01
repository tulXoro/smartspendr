<body>
<div id="budget-creation">
    <h2>Create Monthly Budget</h2>
    <form id="budget-form">
      <label for="category">Category:</label>
      <input type="text" id="category" placeholder="Enter category">
      <label for="amount">Amount:</label>
      <input type="number" id="amount" placeholder="Enter amount">
      <button type="submit">Add Category</button>
    </form>
  </div>

  <div id="budget-management">
    <h2>Manage Monthly Budget</h2>
    <ul id="budget-list">
      <!-- Hardcoded budget categories -->
      <li>
        <span>Category: Groceries</span>
        <span>Amount: $300</span>
        <button>Edit</button>
        <button>Delete</button>
      </li>
      <li>
        <span>Category: Entertainment</span>
        <span>Amount: $100</span>
        <button>Edit</button>
        <button>Delete</button>
      </li>
    </ul>
  </div>
</body>