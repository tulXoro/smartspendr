<body>
    <div id="bill-reminders">
        <h2>Bill Reminders</h2>
        <ul id="bill-list">
        <!-- Hardcoded bill reminders -->
        <li>
            <span>Electricity Bill</span>
            <span>Due: March 15</span>
            <button>Mark as Paid</button>
        </li>
        <li>
            <span>Internet Bill</span>
            <span>Due: March 20</span>
            <button>Mark as Paid</button>
        </li>
        </ul>
    </div>

    <div id="subscription-management">
        <h2>Subscription Management</h2>
        <ul id="subscription-list">
        <!-- Hardcoded subscriptions -->
        <li>
            <span>Netflix</span>
            <span>Status: Active</span>
            <button>Cancel</button>
        </li>
        <li>
            <span>Spotify</span>
            <span>Status: Active</span>
            <button>Cancel</button>
        </li>
        </ul>
    </div>
</body>

<style>
    /* General body styles */
body {
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