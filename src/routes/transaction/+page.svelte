<script>
	import NewExpenseModal from '../../components/NewExpenseModal.svelte';
	import NewIncomeModal from '../../components/NewIncomeModal.svelte';
  import DonutChart from '../../components/DonutChart.svelte';
	import DonutChart2 from '../../components/DonutChart2.svelte';
  import ExpenseItem from '../../components/ExpenseItem.svelte';

  let currentTab = 'Day';
  const tabs = ['Day', 'Week', 'Month', 'Year', 'Period'];
  let currentView = 'Expenses'; 
	let displayedDate = '';
	let totalMoney = 9880;
	let showNewExpenseModal = false;
	let showNewIncomeModal = false;

  const expenses = [
  { category: 'Education', percentage: 83, amount: 100, color: '#2ecc71', icon: '' },
  { category: 'Groceries', percentage: 17, amount: 20, color: '#0B4F6C', icon: '' }
];

  const incomes = [
    { category: 'Paycheck', percentage: 62, amount: 500, color: '#3498db', icon: '' },
    { category: 'Gift', percentage: 38, amount: 300, color: '#9b59b6', icon: '' }
  ];

  const data = {
    labels: ['Education', 'Groceries'],
    datasets: [{
      data: [100, 20],
      backgroundColor: ['#E53E3E', '#CA61C3'],
      hoverBackgroundColor: ['#1CA3A3', '#9BA2FF']
    }]
  };

	  const incomeData = {
    labels: ['Paycheck', 'Gift'],
    datasets: [{
      data: [500, 300],
      backgroundColor: ['#E53E3E', '#CA61C3'],
      hoverBackgroundColor: ['#456990', '#EE85B5']
    }]
  };

// Setup initial date display
  $: {
    const now = new Date();
    switch (currentTab) {
      case 'Day':
        displayedDate = now.toLocaleDateString();
        break;
      case 'Week':
        const startOfWeek = new Date(now.setDate(now.getDate() - now.getDay()));
        const endOfWeek = new Date(startOfWeek.getTime());
        endOfWeek.setDate(startOfWeek.getDate() + 6);
        displayedDate = `${startOfWeek.toLocaleDateString()} - ${endOfWeek.toLocaleDateString()}`;
        break;
      case 'Month':
        const startOfMonth = new Date(now.getFullYear(), now.getMonth(), 1);
        const endOfMonth = new Date(now.getFullYear(), now.getMonth() + 1, 0);
        displayedDate = `${startOfMonth.toLocaleDateString()} - ${endOfMonth.toLocaleDateString()}`;
        break;
      case 'Year':
        const startOfYear = new Date(now.getFullYear(), 0, 1);
        const endOfYear = new Date(now.getFullYear(), 11, 31);
        displayedDate = `${startOfYear.toLocaleDateString()} - ${endOfYear.toLocaleDateString()}`;
        break;
      case 'Period':
        
        displayedDate = 'Custom Period'; // Placeholder
        break;
    }
  }

  function setTab(tab) {
    currentTab = tab;
  }

  function switchView(view) {
    currentView = view;
  }

	function toggleNewExpenseModal(){
		showNewExpenseModal = !showNewExpenseModal;
	}

	function toggleNewIncomeModal(){
		showNewIncomeModal = !showNewIncomeModal;
	}

  function addExpense() {
    console.log("Add new expense");
  }
</script>

<style>


	.total-money {
    text-align: center;
    font-size: 20px;
    color: white; 
    margin-bottom: 10px; 
    font-weight: bold; 
    padding: 10px 0; 
    background-color: #2563EB; 
    border-radius: 5px; 
    box-shadow: 0 2px 4px rgba(0,0,0,0.25); 
}
	
  .card {
    background: white; 
    border-radius: 15px;
    padding: 20px;
    margin: 10px auto;
    max-width: 370px;
    color: white;
		position: relative;
    overflow: visible;
  }
  .tab, .view-toggle {
    padding: 8px 16px;
    margin-right: 4px;
    background-color: #2563EB;
    border: none;
    cursor: pointer;
    color: white;
    border-radius: 5px;
    font-size: 14px;
  }
  .active {
    background-color: #19439e;
  }
  .tab-container {
    display: flex;
    justify-content: space-around;
    margin-bottom: 20px;
  }
	  .date-display {
    text-align: center;
    margin-bottom: 10px; 
    font-size: 14px;
    color: #19439e;
  }
    .greeting {
        color: #19439e;
        font-size: 24px;
        margin-bottom: 5px;
    }
	
button.add-button {
    background-color:  #E53E3E;
    border: none;
    padding: 12px 16px;
    border-radius: 50%;
    font-size: 24px;
    cursor: pointer;
    position: absolute;
    bottom: 149px; 
    right: 18px; 
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}
		@media (max-width: 600px) {
    button.add-button {
        right: 10px; 
        bottom: 50px; 
    }
}
  .chart-container {
    position: relative;
    margin: 20px 0;


  
		
  }
</style>

<div class="card">
  
	<div class="greeting">Hi, Sarah</div>
	  <div class="total-money">
    Total: $ {totalMoney.toLocaleString()}
  </div>
  <div class="tab-container">
    <button on:click={() => switchView('Expenses')} class:active={currentView === 'Expenses'} class="view-toggle">Expenses</button>
    <button on:click={() => switchView('Income')} class:active={currentView === 'Income'} class="view-toggle">Income</button>
  </div>

  {#if currentView === 'Expenses'}
    <div class="tab-container">
      {#each tabs as tab}
        <button class:active={currentTab === tab} class="tab" on:click={() => setTab(tab)}>{tab}</button>
      {/each}
    </div>

		<div class="date-display">{displayedDate}</div>
		
    <div class="chart-container">
      <DonutChart {data} />
    </div>

    {#each expenses as expense}
      <ExpenseItem item={expense} />
    {/each}
<!-- <button class="add-button" on:click={toggleNewExpenseModal} style= "bottom: 148px">+</button> -->
        {#if showNewExpenseModal}
            <NewExpenseModal {addExpense} close={toggleNewExpenseModal} />
        {/if}
  {:else}
   
		    <div class="tab-container">
      {#each tabs as tab}
        <button class:active={currentTab === tab} class="tab" on:click={() => setTab(tab)}>{tab}</button>
      {/each}
    </div>
		<div class="date-display">{displayedDate}</div>
		 <div class="chart-container">
      <DonutChart2 data = {incomeData} />
    </div>
		{#each incomes as income}
      <ExpenseItem item={income} />
    {/each}
		    <!-- <button class="add-button" on:click={toggleNewIncomeModal} style= "bottom: 148px">+</button> -->
        {#if showNewIncomeModal}
            <NewIncomeModal {addExpense} close2={toggleNewIncomeModal} />
        {/if}
  {/if}
</div>