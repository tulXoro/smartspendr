<script>
    import { onMount } from 'svelte';
    import Chart from 'chart.js/auto';
  
    export let data;
  
  
    let canvas;
  
    onMount(() => {
      const ctx = canvas.getContext('2d');
      new Chart(ctx, {
        type: 'doughnut',
        data,
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              position: 'bottom',
            }
          }
        }
      });
    });
  </script>
  
  <canvas bind:this={canvas}></canvas>