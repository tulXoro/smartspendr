<script>
    import Button from '$lib/Button.svelte';
import CreditCard from '$lib/creditmanager/credit_card.svelte';
    import {Modal, FloatingLabelInput, Helper} from 'flowbite-svelte';

    $: cards = [
        {
            cardNumber: '**** **** **** 1234',
            expirationDate: '12/24',
            cvv: '***',
            cardType: 'Visa',
            bankName: 'Bank of America',
        },
        {
            cardNumber: '**** **** **** 5678',
            expirationDate: '12/25',
            cvv: '***',
            cardType: 'Mastercard',
            bankName: 'Chase',
        },
        {
            cardNumber: '**** ******** 9012',
            expirationDate: '12/26',
            cvv: '***',
            cardType: 'American Express',
            bankName: 'Wells Fargo',
        },
    ]

    let showModal = false;

    function addCard(e) {
        e.preventDefault();
        const form = e.target;
        const cardNumber = form['Card Number'].value;
        const expirationDate = form['Expiration Date'].value;
        const cvv = form['CVV'].value;
        const cardType = form['Card Type'].value;
        const bankName = form['Bank Name'].value;

        cards = [...cards, {cardNumber, expirationDate, cvv, cardType, bankName}];
        showModal = false;
    }
</script>



<main class="flex flex-col h-screen items-center">
    <h1 class="">
        Credit Card Management
    </h1>

    <div id="creditcardcontainer" class="grid lg:grid-cols-2 sm:grid-cols-1" >
        {#each cards as card}
            <CreditCard
                cardNumber={card.cardNumber}
                expirationDate={card.expirationDate}
                cvv={card.cvv}
                cardType={card.cardType}
                bankName={card.bankName} />
        {/each}

        <div class="flex justify-center">
            <button on:click={() => showModal = true} class="w-50 mx-5 my-3 lg:w-80 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mb-32">
                Add New Card
            </button>
        </div>

        <Modal bind:open={showModal} title="Add New Card" autoclose>
            <form class="grid gap-3">
                <div class="grid grid-cols-2 gap-3">
                    <FloatingLabelInput style="outlined" type="text" name="Card Number" label="Card Number" placeholder="Card Number" min={16} max={16} required>
                        <Helper>Card Number</Helper>
                    </FloatingLabelInput>
                    <FloatingLabelInput class="max-w-2" style="outlined" type="text" name="CVV" label="CVV" placeholder="CVV" min={3} max={3}>
                        <Helper>CVV</Helper>
                    </FloatingLabelInput>
                    <FloatingLabelInput class="w-3" style="outlined" type="date" name="Expiration Date" label="Expiration Date" placeholder="Expiration Date">
                        <Helper>Expiration</Helper>
                    </FloatingLabelInput>
                </div>



                <div class="grid grid-cols-2 gap-3">
                    <FloatingLabelInput style="outlined" type="text" name="Card Type" label="Card Type" placeholder="Card Type">
                        <Helper>Card Type</Helper>
                    </FloatingLabelInput>
                    <FloatingLabelInput style="outlined" type="text" name="Bank Name" label="Bank Name" placeholder="Bank Name">
                        <Helper>Bank Name</Helper>
                    </FloatingLabelInput>
                </div>

                <div class="grid grid-cols-2">
                    <button class="w-fit bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded self-center" on:submit={addCard}>
                        Add Card
                    </button>
                    <button class="w-fit bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded self-center" on:click={() => showModal = false} >
                        Cancel
                    </button>
                </div>

            </form>
        </Modal>
    </div>

</main>
