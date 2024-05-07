
<script>
   import RobotIcon from "$lib/assets/robot.svg";
   import UserIcon from "$lib/assets/user.svg";
   export let sender = "AI Assistant";
   export let text = "Hello, how can I help you today?";
   export let time;
</script>

<div class="flex items-start gap-2.5 py-2">
   {#if sender === "AI Assistant"}
      <img class="w-8 h-8 rounded-full" src={RobotIcon} alt="RobotIcon">
   {:else}
      <img class="w-8 h-8 rounded-full" src={UserIcon} alt="UserIcon">
   {/if}
    <div class="flex flex-col w-full max-w-[320px] leading-1.5 p-4 border-gray-200 bg-gray-100 rounded-e-xl rounded-es-xl dark:bg-gray-700">
       <div class="flex items-center space-x-2 rtl:space-x-reverse">
          <span class="text-sm font-semibold text-gray-900 dark:text-white">{sender}</span>
          <span class="text-sm font-normal text-gray-500 dark:text-gray-400">{time}</span>
       </div>

       <p class="text-sm font-normal py-2.5 text-gray-900 dark:text-white">
         {text}
       </p>

       {#if sender !== "AI Assistant"}
       <span class="text-sm font-normal text-gray-500 dark:text-gray-400">Delivered</span>
       {/if}
    </div>
 </div>
