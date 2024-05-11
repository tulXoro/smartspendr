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

<style>
    /* General body styles */
    main {
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        background-color: #e8f5e9; /* Soft green background updated to neutral */
        color: #2563EB; /* Blue text color */
        margin: 0;
        padding: 20px;
    }

    /* Headings with a red color */
    h2 {
        color: #E53E3E; /* Updated from green to red */
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
        border-left: 5px solid #2563EB; /* Updated accent color to blue */
        margin-bottom: 20px;
        padding: 20px;
        box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }

    /* Professional and more appealing button styles */
    button {
        font-size: 1rem;
        padding: 10px 20px;
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
        max-width: 800px; /* Limiting max width for better readability */
        padding: 20px;
        background-color: #fff; /* Kept the background white for better contrast */
        border-radius: 8px;
        box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    }
</style>
