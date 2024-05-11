
<script>
  import Chart from '../../components/Chart.svelte';
  import ExpenseList from '../../components/ExpenseList.svelte';
  import { data } from '../../components/data.js';

  let expenses = data.labels.map((label, index) => ({
    id: index,
    name: label,
    amount: data.datasets[0].data[index],
    color: data.datasets[0].backgroundColor[index],
    expanded: false,
    details: data.details[index] 
  }));
</script>

<style>
.page {
  display: grid;
  place-items: center;
  height: 100vh;
  padding: 2rem;
  box-sizing: border-box;
}

.container{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
}

h1{
  color: #333;
}
</style>

<div class="page">
  <div class="container">
    <div style="height: 400px; width: 100%;">
      <Chart />
    </div>
    <ExpenseList {expenses} />
    <div>
      <a href="budget" type="button" class="mt-4 inline-flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-blue-500 hover:bg-blue-700">
        <span class="text-white">Add Budget</span>
      </a>
    </div>
  </div>
</div>