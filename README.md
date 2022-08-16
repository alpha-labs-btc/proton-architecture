![proton_initialize](https://github.com/0xmodule/proton-architechture/blob/main/pictures/twitter-bg.png?raw=true)
## <a name='TableofContents'></a>Table of Contents

* [1. Main Function](#1-main-function)
    * [1.1 Proton Initialize](#11-proton_initialize)
    * [1.2 Proton Initialize](#11-proton_initialize)

## Main Function
### `proton_initialize`

![proton_initialize](https://github.com/0xmodule/proton-architechture/blob/main/pictures/proton_initialize.png?raw=true)

<pre><code><b>public</b> <b>fun</b> <a href="sale.md#0xcafe_sale_proton_initialize">proton_initialize</a>(owner: &<a href="">signer</a>)
</code></pre>

### `create_sale`

![create_sale](https://github.com/0xmodule/proton-architechture/blob/main/pictures/create_sale.png?raw=true)

<pre><code><b>public</b> <b>fun</b> <a href="sale.md#0xcafe_sale_init_event_manager">proton_initialize</a>(owner: &<a href="">signer</a>)
</code></pre>

<pre><code><b>public</b> <b>fun</b> <a href="sale.md#0xcafe_sale_create_sale">create_sale</a>&lt;SaleCoinType, PurchaseCoinType&gt;(<a href="">account</a>: &<a href="">signer</a>, name: <a href="">vector</a>&lt;u8&gt;, sale_coin_amount: u64, sale_rate: u8, sale_start_time: u64, whitelist_duration: u64, sale_duration: u64, softcap: u64, hardcap: u64, vesting_tge_duration: u64, tge_percent: u8, vesting_cycle_duration: u64, vesting_cycle_percent: u8)
</code></pre>

### `register`

![register](https://github.com/0xmodule/proton-architechture/blob/main/pictures/register.png?raw=true)

<pre><code><b>fun</b> <a href="sale.md#0xcafe_sale_check_sale_store_exists">check_sale_store_exists</a>&lt;SaleCoinType, PurchaseCoinType&gt;(<a href="">account</a>: &<a href="">signer</a>)
</code></pre>

### `add_whitelist`

![add_whitelist](https://github.com/0xmodule/proton-architechture/blob/main/pictures/add_whitelist.png?raw=true)

<pre><code><b>public</b> <b>fun</b> <a href="whitelist.md#0xcafe_whitelist_add_whitelist">add_whitelist</a>&lt;S_ID: <b>copy</b>, drop&gt;(<a href="">account</a>: &<a href="">signer</a>, s_id: S_ID, addresses: <a href="">vector</a>&lt;<b>address</b>&gt;)
</code></pre>

### `contribute`

![contribute](https://github.com/0xmodule/proton-architechture/blob/main/pictures/contribute.png?raw=true)

<pre><code><b>public</b> <b>fun</b> <a href="sale.md#0xcafe_sale_contribute">contribute</a>&lt;SaleCoinType, PurchaseCoinType&gt;(<a href="">account</a>: &<a href="">signer</a>, creator: <b>address</b>, name: <a href="">vector</a>&lt;u8&gt;, amount: u64, is_whitelist_round: bool)
</code></pre>

### `end_sale`

![end_sale](https://github.com/0xmodule/proton-architechture/blob/main/pictures/end_sale.png?raw=true)

<pre><code><b>public</b> <b>fun</b> <a href="sale.md#0xcafe_sale_end_sale">end_sale</a>&lt;SaleCoinType, PurchaseCoinType&gt;(<a href="">account</a>: &<a href="">signer</a>, creator: <b>address</b>, name: <a href="">vector</a>&lt;u8&gt;)
</code></pre>

### `claim`

![claim](https://github.com/0xmodule/proton-architechture/blob/main/pictures/claim.png?raw=true)

<pre><code><b>public</b> <b>fun</b> <a href="sale.md#0xcafe_sale_claim">claim</a>&lt;SaleCoinType, PurchaseCoinType&gt;(<a href="">account</a>: &<a href="">signer</a>, creator: <b>address</b>, name: <a href="">vector</a>&lt;u8&gt;)
</code></pre>
