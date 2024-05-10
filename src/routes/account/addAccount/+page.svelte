<script>
    let accountName = '';
    let cardNumber = '';
    let expiryDate = '';
    let cvv = '';
  
    function handleSubmit() {
      // handle form submission
      console.log({ accountName, cardNumber, expiryDate, cvv });
    }
  </script>
  
  <div class="page-container">
    <div>
    <a href="/account" class="back-button">Back to Account</a>
    </div>

    <div>    
        <h1>
      Add Account page
    </h1>
  </div>
  <form on:submit|preventDefault={handleSubmit}>
    <label>
      Account Name:
      <input type="text" bind:value={accountName} required />
    </label>
  
    <label>
      Card Number:
      <input type="text" bind:value={cardNumber} required />
    </label>
  
    <label>
      Expiry Date:
      <input type="text" bind:value={expiryDate} required />
    </label>
  
    <label>
      CVV:
      <input type="text" bind:value={cvv} required />
    </label>
  
    <div class="submit-button-container">
      <button type="submit">Add Account</button>
    </div>
  </form>

    </div>
  
  <style>


  @media (max-width: 600px) {
    .back-button {
      position: relative;
      display: block;
      margin-bottom: 1rem;
    }

    .page-container {
      padding-top: 0;
    }
  
  }
    .page-container {
    padding-top: 5rem; /* adjust as needed */
    font-family: Arial, sans-serif;
    max-width: 600px;
    margin: 0 auto;
  }

  .back-button {
    position: absolute;
    top: 0;
    left: 0;
    background-color: #007bff;
    border: none;
    border-radius: 4px;
    padding: 10px 20px;
    cursor: pointer;
    color: white;
  }

  h1 {
    text-align: center;
    color: #343a40;
  }

  form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  label {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  input {
    padding: 10px;
    border: 1px solid #ced4da;
    border-radius: 4px;
  }

  .submit-button-container {
    display: flex;
    justify-content: center;
    margin-top: 1rem;
  }

  .submit-button-container button {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 10px 20px;
    cursor: pointer;
    border-radius: 4px;
  }

  .submit-button-container button:hover {
    background-color: #0056b3;
  }
  </style>
