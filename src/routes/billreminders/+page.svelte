<main>
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
</main>

/*<style>
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
    #subscription-management {
        margin: auto;
        max-width: 800px; /* Limiting max width for better readability */
        padding: 20px;
        background-color: #fff;
        border-radius: 8px;
        box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    }
</style>*/

<style>
/* General body styles */
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f5f5f5; /* Soft green background */
  color: #010101;
  margin: 0;
  padding: 10px; /* Adjusted padding for smaller screens */
}

/* Headings with a deeper green color */
h2 {
  color: #000000;
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
  border-left: 5px solid #121212; /* Green accent on the side */
  margin-bottom: 10px; /* Adjusted margin for smaller screens */
  padding: 15px; /* Adjusted padding for smaller screens */
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

/* Professional and more appealing button styles */
button {
  font-size: 1rem;
  padding: 8px 16px; /* Adjusted padding for smaller screens */
  background-color: #000000;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #0a0a0a;
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
