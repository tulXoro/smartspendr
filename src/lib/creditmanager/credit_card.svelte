<script>
    import { Card, Tabs, TabItem, Chart, A, Button, Dropdown, DropdownItem, Label, Toggle, Checkbox, Modal, Range } from 'flowbite-svelte';

    export let cardNumber = '**** **** **** 1234';
    export let expirationDate = '12/24';
    export let cvv = '***';
    export let cardType = 'Visa';
    export let bankName = 'Bank of America';
    let bankPhone = '+1234567890';

    const options = {
    colors: ['#1A56DB', '#FDBA8C'],
    series: [
      {
        name: 'Food',
        color: '#1A56DB',
        data: [
          { x: 'Mon', y: 231 },
          { x: 'Tue', y: 122 },
          { x: 'Wed', y: 63 },
          { x: 'Thu', y: 421 },
          { x: 'Fri', y: 122 },
          { x: 'Sat', y: 323 },
          { x: 'Sun', y: 111 }
        ]
      },
      {
        name: 'Fuel',
        color: '#FDBA8C',
        data: [
          { x: 'Mon', y: 232 },
          { x: 'Tue', y: 113 },
          { x: 'Wed', y: 341 },
          { x: 'Thu', y: 224 },
          { x: 'Fri', y: 522 },
          { x: 'Sat', y: 411 },
          { x: 'Sun', y: 243 }
        ]
      }
    ],
    chart: {
      type: 'bar',
      height: '70%',
      fontFamily: 'Inter, sans-serif',
      toolbar: {
        show: false
      }
    },
    plotOptions: {
      bar: {
        horizontal: false,
        columnWidth: '70%',
        borderRadiusApplication: 'end',
        borderRadius: 8
      }
    },
    tooltip: {
      shared: true,
      intersect: false,
      style: {
        fontFamily: 'Inter, sans-serif'
      }
    },
    states: {
      hover: {
        filter: {
          type: 'darken',
          value: 1
        }
      }
    },
    stroke: {
      show: true,
      width: 0,
      colors: ['transparent']
    },
    grid: {
      show: false,
      strokeDashArray: 4,
      padding: {
        left: 2,
        right: 2,
        top: -14
      }
    },
    dataLabels: {
      enabled: false
    },
    legend: {
      show: false
    },
    xaxis: {
      floating: false,
      labels: {
        show: true,
        style: {
          fontFamily: 'Inter, sans-serif',
          cssClass: 'text-xs font-normal fill-gray-500 dark:fill-gray-400'
        }
      },
      axisBorder: {
        show: false
      },
      axisTicks: {
        show: false
      }
    },
    yaxis: {
      show: false
    },
    fill: {
      opacity: 1
    }
  };
  let freezeModal = false;
  let autoFreezeModal = false;

  $: freeze = false;
  $: autoFreeze = false;

  function openFreezeModal() {
    if(freeze) {
        return;
    }

    freezeModal = true;
  }

  function openAutoFreezeModal() {
    if(autoFreeze) {
        return;
    }
    autoFreezeModal = true;
  }

    function enableFreeze() {
        freeze = true;
        freezeModal = false;
    }

    function disableFreeze() {
        freeze = false;
        freezeModal = false;
    }

    function enableAutoFreeze() {
        autoFreeze = true;
        autoFreezeModal = false;
    }

    function disableAutoFreeze() {
        autoFreeze = false;
        autoFreezeModal = false;
    }
</script>


<Card class="w-80 h-80">
    <Tabs tabStyle="full" defaultClass="flex w-fit rounded-lg divide-x rtl:divide-x-reverse divide-gray-200 shadow dark:divide-gray-700">
        <TabItem open>
          <span slot="title">Info</span>
            <div>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Card Number:</b>
                    {cardNumber}
                </p>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Expiration Date:</b>
                    {expirationDate}
                </p>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>CVV:</b>
                    {cvv}
                </p>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Card Type:</b>
                    {cardType}
                </p>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Bank Name:</b>
                    {bankName}
                </p>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Bank Phone:</b>
                    <A href="tel:+1234567890">{bankPhone}</A>
                </p>
            </div>
            <div class="grid grid-cols-2 gap-32 p-1">
              <Button class="w-fit h-fit px-1 py-2">View Transactions</Button>
              <Button class="w-fit px-1 py-2 h-fit self-end">Reveal</Button>
            </div>

        </TabItem>
        <TabItem class="p-0">
          <span slot="title">Spending</span>

            <Chart {options} />
            <Button class="text-sm font-medium">Last 7 days</Button>
            <Dropdown class="w-40" offset={-6}>
              <DropdownItem>Yesterday</DropdownItem>
              <DropdownItem>Today</DropdownItem>
              <DropdownItem>Last 7 days</DropdownItem>
              <DropdownItem>Last 30 days</DropdownItem>
              <DropdownItem>Last 90 days</DropdownItem>
            </Dropdown>

        </TabItem>
        <TabItem>
            <span slot="title">Control</span>
            <p class="text-sm text-gray-500 dark:text-gray-400 break-normal grid grid-cols-2 grid-rows-2 gap-y-16 gap-x-3">
                <Toggle on:click={openFreezeModal} bind:checked={freeze} class="text-normal font-normal" color = "teal"><span>Freeze Card</span></Toggle>

                <Modal title="Terms of Service" bind:open={freezeModal} autoclose>
                    <p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">Are you sure you want to freeze this card?</p>
                    <svelte:fragment slot="footer">
                      <Button on:click={enableFreeze} >Yes</Button>
                      <Button on:click={disableFreeze} color="alternative">Decline</Button>
                    </svelte:fragment>
                </Modal>
                <Toggle on:click= {openAutoFreezeModal} bind:checked={autoFreeze} class="text-normal font-normal" color = "teal"><span>Auto Freeze Card</span></Toggle>
                <Modal title="Terms of Service" bind:open={autoFreezeModal} autoclose>
                    <p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">Are you sure you want to enable auto freeze this card?</p>
                    <Label>Freeze Threshold:</Label>
                    <Range size="lg" value={0} />
                    <svelte:fragment slot="footer">
                      <Button on:click={enableAutoFreeze}> Accept </Button>
                      <Button on:click={disableAutoFreeze} color="alternative"> Decline</Button>
                    </svelte:fragment>
                </Modal>

                <Button class="w-fit bg-green-600">Edit</Button>
                <Button class="w-fit bg-red-700">Remove</Button>
            </p>
          </TabItem>
      </Tabs>
</Card>