<main>
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
</main>

<style>
    /* General body styles */
main {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #e8f5e9; /* Soft green background */
  color: #333;
  margin: 0;
  padding: 20px;
}

/* Headings with a deeper green color */
h2 {
  color: #1b5e20;
  text-align: center;
}

/* Styling for lists to make them fill out more space */
ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

/* List items with more prominent styling */
li {
  background-color: #ffffff;
  border-left: 5px solid #4caf50; /* Green accent on the side */
  margin-bottom: 20px;
  padding: 20px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

/* Professional and more appealing button styles */
button {
  font-size: 1rem;
  padding: 10px 20px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #388e3c;
}

/* Full-width container for each section */
#bill-reminders, #subscription-management {
  margin: auto;
  max-width: 800px; /* Limiting max width for better readability */
  padding: 20px;
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}
</style>