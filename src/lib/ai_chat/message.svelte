<script>
   import RobotIcon from "$lib/assets/robot.svg";
   import UserIcon from "$lib/assets/user.svg";
   export let sender = "AI Assistant";
   export let text = "Hello, how can I help you today? You can ask me to do anything like give you budget tips, generate reports or analyze your spending habits!";
   export let time;
</script>

<div class="flex items-start gap-2.5 py-2">
   {#if sender === "AI Assistant"}
      <img class="w-8 h-8 rounded-full" src={RobotIcon} alt="RobotIcon">
   {/if}
    <div 
      class="flex flex-col w-full max-w-[320px] leading-1.5 p-4 border-gray-200 chat-box rounded-b-xl"
      class:rounded-r-xl={sender === "AI Assistant"}
      class:rounded-l-xl={sender !== "AI Assistant"}
      >
       <div class="flex items-center space-x-2 rtl:space-x-reverse">
          <span class="text-sm font-semibold">{sender}</span>
          <span class="text-sm font-normal">{time}</span>
       </div>

       <p class="text-sm font-normal py-2.5">
         {text}
       </p>

       {#if sender !== "AI Assistant"}
       <span class="text-sm font-normal">Delivered</span>
       {/if}
    </div>
   {#if sender !== "AI Assistant"}
      <img class="w-8 h-8 rounded-full" src={UserIcon} alt="UserIcon">
   {/if}
 </div>

 <style>
  .chat-box {
    background-color: #E53E3E;
    color: white; /* complimentary blue color */
  }
  </style>