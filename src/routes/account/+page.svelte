
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
    <h1 class="text-3xl font-bold underline">
      Account page
    </h1>
    <div style="height: 400px; width: 100%;">
      <Chart />
    </div>
    <ExpenseList {expenses} />
  </div>
</div>