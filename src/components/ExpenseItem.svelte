<script>
    export let item;
		
</script>

<style>
  .legend {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #2ecc71; 
    padding: 8px 12px; 
    border-radius: 4px;
    margin-bottom: 5px; 
    color: white;
    font-size: 16px;
  }

  .category {
    display: flex;
    align-items: center;
    flex: 1;
  }

  .icon {
    width: 24px;
    height: 24px;
    background-size: cover;
    background-position: center;
    margin-right: 10px;
  }

  .stats {
    display: flex;
    align-items: center; 
    min-width: 130px; 
  }

  .percentage, .amount {
    background-color: #27ae60; 
    padding: 4px 8px;
    border-radius: 4px;
    margin-left: 10px; 
  }

  
  .category, .percentage, .amount {
    white-space: nowrap;
  }
</style>

<div class="legend">
    <div class="category">
      <div class="icon" style="background-image: url('{item.icon}');"></div>
      {item.category}
    </div>
    <div class="stats">
      <div class="percentage">{item.percentage}%</div>
      <div class="amount">${item.amount}</div>
    </div>
</div>