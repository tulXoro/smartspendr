<script>
  import backArrow from '$lib/backArrow.png';
  export let typeOf = 'icon'

</script>
<main>
  <a href="/account" class={typeOf}>
    <img src={backArrow} alt="back arrow" />
</a>
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
  img {
    height: auto;
    width: 4vw;
  }
  a {
    width: 10vw;
    display: flex;
    margin-top: 20px;
  }
  /* General body styles */
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f5f5f5; /* Neutral background */
    color: #2563EB; /* Updated text color to blue */
    margin: 0;
    padding: 10px; /* Adjusted padding for smaller screens */
  }

  /* Headings with a deeper color */
  h2 {
    color: #E53E3E; /* Updated color to red */
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
    border-left: 5px solid #2563EB; /* Updated accent to blue */
    margin-bottom: 10px; /* Adjusted margin for smaller screens */
    padding: 15px; /* Adjusted padding for smaller screens */
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }

  /* Professional and more appealing button styles */
  button {
    font-size: 1rem;
    padding: 8px 16px; /* Adjusted padding for smaller screens */
    background-color: #2563EB; /* Updated button color to blue */
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  button:hover {
    background-color: #1D4ED8; /* A darker shade of blue for hover */
  }

  /* Full-width container for each section */
  #subscription-management {
    margin: auto;
    max-width: 100%; /* Adjusted to full width for smaller screens */
    padding: 10px; /* Adjusted padding for smaller screens */
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  }
</style>
