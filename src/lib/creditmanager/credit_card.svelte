<script>
import { Card, Tabs, TabItem } from 'flowbite-svelte';
</script>


<Card class="w-80 h-60">
    <Tabs tabStyle="full" defaultClass="flex w-fit rounded-lg divide-x rtl:divide-x-reverse divide-gray-200 shadow dark:divide-gray-700">
        <TabItem open>
          <span slot="title">Info</span>
            <div>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Card Number:</b>
                    **** **** **** 1234
                </p>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Expiration Date:</b>
                    12/24
                </p>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>CVV:</b>
                    ***
                </p>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Card Type:</b>
                    Visa
                </p>

            </div>
            <button>
                Reveal
            </button>
        </TabItem>
        <TabItem class="p-0">
          <span slot="title">Spending</span>
            <div>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Current Balance:</b>
                    $1000
                </p>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Available Credit:</b>
                    $5000
                </p>
                <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Spent This Month:</b>
                    $500
                </p>
            </div>
            <button>
                View Transactions
            </button>

        </TabItem>
        <TabItem>
            <span slot="title">Control</span>
            <p class="text-sm text-gray-500 dark:text-gray-400 break-normal">
                <button>
                    Edit
                </button>
                <button>
                    Freeze
                </button>
                <button>
                    Automatically Freeze
                </button>
                <button>
                    Remove
                </button>
            </p>
          </TabItem>
      </Tabs>
</Card>