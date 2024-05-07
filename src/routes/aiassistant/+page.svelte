<script lang="ts">
    import MessageBubble from '$lib/ai_chat/message.svelte';

    let messages = [
        {
            sender: "AI Assistant",
            text: "Hello, how can I help you today?",
            time: new Date().toLocaleTimeString().replace(/([\d]+:[\d]{2})(:[\d]{2})(.*)/, "$1$3")
        }
    ];

    function sendMessage(event) {
        event.preventDefault();
        const chat = event.target.chat;
        const message = chat.value;
        if (!message) return;
        chat.value = "";
        messages = [
            ...messages,
            {
                sender: "You",
                text: message,
                time: new Date().toLocaleTimeString().replace(/([\d]+:[\d]{2})(:[\d]{2})(.*)/, "$1$3")
            }
        ];
    }
</script>

<main class="flex justify-center max-h-screen overflow-hidden">

    <div id="chat_interface" class="flex flex-col rounded-2xl overflow-y-auto relative p-4">
        <div class="flex flex-col overflow-y-auto mb-auto">
            {#each messages as message}
            <MessageBubble
                sender={message.sender}
                text={message.text}
                time={message.time}
            />
        {/each}
        </div>


        <form on:submit={sendMessage}>
            <label for="chat" class="sr-only">Your message</label>
            <div class="flex items-center px-3 py-2 rounded-lg bg-gray-50 dark:bg-gray-700">
                <input type="textarea" id="chat" class="block mx-4 p-2.5 w-full text-sm text-gray-900 bg-white rounded-lg border border-gray-300 focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="Your message..." />
                    <button type="submit" class="inline-flex justify-center p-2 text-blue-600 rounded-full cursor-pointer hover:bg-blue-100 dark:text-blue-500 dark:hover:bg-gray-600">
                    <svg class="w-5 h-5 rotate-90 rtl:-rotate-90" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 18 20">
                        <path d="m17.914 18.594-8-18a1 1 0 0 0-1.828 0l-8 18a1 1 0 0 0 1.157 1.376L8 18.281V9a1 1 0 0 1 2 0v9.281l6.758 1.689a1 1 0 0 0 1.156-1.376Z"/>
                    </svg>
                    <span class="sr-only">Send message</span>
                </button>
            </div>
        </form>
    </div>
</main>

<style>
#chat_interface {
    height: calc(100vh - 60px - 4em);
    border: 1px solid #e2e8f0;

}
</style>