<script>
    import CreditCard from '$lib/creditmanager/credit_card.svelte';
</script>



<main class="flex flex-col h-screen items-center">
    <h1 class="text-3xl font-bold underline pb-10">
        Credit Card Management Page
    </h1>

    <div id="creditcardcontainer" class="grid grid-cols-2 gap-8" >
        <CreditCard />
        <CreditCard />
        <CreditCard />
    </div>

</main>
