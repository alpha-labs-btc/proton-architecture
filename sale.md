
<a name="0xcafe_sale"></a>

# Module `0xcafe::sale`



-  [Struct `SaleId`](#0xcafe_sale_SaleId)
-  [Struct `VestingInfo`](#0xcafe_sale_VestingInfo)
-  [Resource `ProtonEvent`](#0xcafe_sale_ProtonEvent)
-  [Struct `AddWhitelistEvent`](#0xcafe_sale_AddWhitelistEvent)
-  [Struct `EndSaleSuccessEvent`](#0xcafe_sale_EndSaleSuccessEvent)
-  [Struct `CreateSaleEvent`](#0xcafe_sale_CreateSaleEvent)
-  [Struct `ContributeEvent`](#0xcafe_sale_ContributeEvent)
-  [Struct `RefundEvent`](#0xcafe_sale_RefundEvent)
-  [Struct `ClaimEvent`](#0xcafe_sale_ClaimEvent)
-  [Struct `SaleInfo`](#0xcafe_sale_SaleInfo)
-  [Struct `SaleStatus`](#0xcafe_sale_SaleStatus)
-  [Resource `SaleStore`](#0xcafe_sale_SaleStore)
-  [Resource `UserSaleStore`](#0xcafe_sale_UserSaleStore)
-  [Struct `ClaimTicket`](#0xcafe_sale_ClaimTicket)
-  [Struct `PurchaseTicket`](#0xcafe_sale_PurchaseTicket)
-  [Constants](#@Constants_0)
-  [Function `assert_proton_sale`](#0xcafe_sale_assert_proton_sale)
-  [Function `check_sale_store_exists`](#0xcafe_sale_check_sale_store_exists)
-  [Function `proton_initialize`](#0xcafe_sale_proton_initialize)
-  [Function `create_sale`](#0xcafe_sale_create_sale)
-  [Function `end_sale`](#0xcafe_sale_end_sale)
-  [Function `claim`](#0xcafe_sale_claim)
-  [Function `refund`](#0xcafe_sale_refund)
-  [Function `withdraw_sale_raw`](#0xcafe_sale_withdraw_sale_raw)
-  [Function `withdraw_purchase_raw`](#0xcafe_sale_withdraw_purchase_raw)
-  [Function `contribute`](#0xcafe_sale_contribute)
-  [Function `get_sale_info`](#0xcafe_sale_get_sale_info)
-  [Function `is_account_whitelisted`](#0xcafe_sale_is_account_whitelisted)
-  [Function `get_sale_id`](#0xcafe_sale_get_sale_id)
-  [Function `get_sale_status`](#0xcafe_sale_get_sale_status)
-  [Function `get_vesting_claimable`](#0xcafe_sale_get_vesting_claimable)
-  [Function `create_vesting`](#0xcafe_sale_create_vesting)


<pre><code><b>use</b> <a href="">0x1::coin</a>;
<b>use</b> <a href="">0x1::event</a>;
<b>use</b> <a href="">0x1::signer</a>;
<b>use</b> <a href="">0x1::string</a>;
<b>use</b> <a href="">0x1::table</a>;
<b>use</b> <a href="">0x1::timestamp</a>;
<b>use</b> <a href="">0x1::type_info</a>;
<b>use</b> <a href="whitelist.md#0xcafe_whitelist">0xcafe::whitelist</a>;
</code></pre>



<a name="0xcafe_sale_SaleId"></a>

## Struct `SaleId`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_SaleId">SaleId</a> <b>has</b> <b>copy</b>, drop, store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>name: <a href="_String">string::String</a></code>
</dt>
<dd>

</dd>
<dt>
<code>creator: <b>address</b></code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_VestingInfo"></a>

## Struct `VestingInfo`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_VestingInfo">VestingInfo</a> <b>has</b> store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>tge_time: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>tge_percent: u8</code>
</dt>
<dd>

</dd>
<dt>
<code>vesting_cycle_duration: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>vesting_cycle_percent: u8</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_ProtonEvent"></a>

## Resource `ProtonEvent`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_ProtonEvent">ProtonEvent</a> <b>has</b> key
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>add_whitelist_events: <a href="_EventHandle">event::EventHandle</a>&lt;<a href="sale.md#0xcafe_sale_AddWhitelistEvent">sale::AddWhitelistEvent</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>end_sale_sucess_events: <a href="_EventHandle">event::EventHandle</a>&lt;<a href="sale.md#0xcafe_sale_EndSaleSuccessEvent">sale::EndSaleSuccessEvent</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>create_sale_events: <a href="_EventHandle">event::EventHandle</a>&lt;<a href="sale.md#0xcafe_sale_CreateSaleEvent">sale::CreateSaleEvent</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>contribute_events: <a href="_EventHandle">event::EventHandle</a>&lt;<a href="sale.md#0xcafe_sale_ContributeEvent">sale::ContributeEvent</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>refund_events: <a href="_EventHandle">event::EventHandle</a>&lt;<a href="sale.md#0xcafe_sale_RefundEvent">sale::RefundEvent</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>claim_events: <a href="_EventHandle">event::EventHandle</a>&lt;<a href="sale.md#0xcafe_sale_ClaimEvent">sale::ClaimEvent</a>&gt;</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_AddWhitelistEvent"></a>

## Struct `AddWhitelistEvent`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_AddWhitelistEvent">AddWhitelistEvent</a> <b>has</b> drop, store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>s_id: <a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a></code>
</dt>
<dd>

</dd>
<dt>
<code>new_addresses: <a href="">vector</a>&lt;<b>address</b>&gt;</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_EndSaleSuccessEvent"></a>

## Struct `EndSaleSuccessEvent`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_EndSaleSuccessEvent">EndSaleSuccessEvent</a> <b>has</b> drop, store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>s_id: <a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a></code>
</dt>
<dd>

</dd>
<dt>
<code>account_address: <b>address</b></code>
</dt>
<dd>

</dd>
<dt>
<code>contributed: u64</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_CreateSaleEvent"></a>

## Struct `CreateSaleEvent`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_CreateSaleEvent">CreateSaleEvent</a> <b>has</b> drop, store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>s_id: <a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a></code>
</dt>
<dd>

</dd>
<dt>
<code>hardcap: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>softcap: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>sale_start_time: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>account_address: <b>address</b></code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_ContributeEvent"></a>

## Struct `ContributeEvent`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_ContributeEvent">ContributeEvent</a> <b>has</b> drop, store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>s_id: <a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a></code>
</dt>
<dd>

</dd>
<dt>
<code>account_address: <b>address</b></code>
</dt>
<dd>

</dd>
<dt>
<code>amount: u64</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_RefundEvent"></a>

## Struct `RefundEvent`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_RefundEvent">RefundEvent</a> <b>has</b> drop, store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>s_id: <a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a></code>
</dt>
<dd>

</dd>
<dt>
<code>account_address: <b>address</b></code>
</dt>
<dd>

</dd>
<dt>
<code>amount: u64</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_ClaimEvent"></a>

## Struct `ClaimEvent`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_ClaimEvent">ClaimEvent</a> <b>has</b> drop, store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>s_id: <a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a></code>
</dt>
<dd>

</dd>
<dt>
<code>account_address: <b>address</b></code>
</dt>
<dd>

</dd>
<dt>
<code>amount: u64</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_SaleInfo"></a>

## Struct `SaleInfo`

This struct store all constant properties of a sale


<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_SaleInfo">SaleInfo</a> <b>has</b> store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>sale_coin_type_info: <a href="_TypeInfo">type_info::TypeInfo</a></code>
</dt>
<dd>

</dd>
<dt>
<code>sale_coin_amount: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>purchase_coin_type_info: <a href="_TypeInfo">type_info::TypeInfo</a></code>
</dt>
<dd>

</dd>
<dt>
<code>sale_rate: u8</code>
</dt>
<dd>

</dd>
<dt>
<code>sale_start_time: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>whitelist_duration: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>sale_duration: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>softcap: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>hardcap: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>vesting_tge_duration: u64</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_SaleStatus"></a>

## Struct `SaleStatus`

This struct store all dynamic properties of a tier
In MVP version we just define one tier


<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_SaleStatus">SaleStatus</a> <b>has</b> store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>contributed: u64</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_SaleStore"></a>

## Resource `SaleStore`

Resource store in saler account
Sale Info contain all constant infomation of a sale
Sale Status contain all dynamic infomation of a sale
Vesting info contain infomation of the time after sale
Coins store Coin for sale of saler


<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_SaleStore">SaleStore</a>&lt;SaleCoinType, PurchaseCoinType&gt; <b>has</b> key
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>sale_infos: <a href="_Table">table::Table</a>&lt;<a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a>, <a href="sale.md#0xcafe_sale_SaleInfo">sale::SaleInfo</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>sale_status: <a href="_Table">table::Table</a>&lt;<a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a>, <a href="sale.md#0xcafe_sale_SaleStatus">sale::SaleStatus</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>sale_coins: <a href="_Table">table::Table</a>&lt;<a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a>, <a href="_Coin">coin::Coin</a>&lt;SaleCoinType&gt;&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>purchase_coins: <a href="_Table">table::Table</a>&lt;<a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a>, <a href="_Coin">coin::Coin</a>&lt;PurchaseCoinType&gt;&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>vesting_infos: <a href="_Table">table::Table</a>&lt;<a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a>, <a href="sale.md#0xcafe_sale_VestingInfo">sale::VestingInfo</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>claim_tickets: <a href="_Table">table::Table</a>&lt;<a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a>, <a href="sale.md#0xcafe_sale_ClaimTicket">sale::ClaimTicket</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>purchase_tickets: <a href="_Table">table::Table</a>&lt;<a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a>, <a href="sale.md#0xcafe_sale_PurchaseTicket">sale::PurchaseTicket</a>&gt;</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_UserSaleStore"></a>

## Resource `UserSaleStore`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_UserSaleStore">UserSaleStore</a>&lt;SaleCoinType, PurchaseCoinType&gt; <b>has</b> key
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>claim_tickets: <a href="_Table">table::Table</a>&lt;<a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a>, <a href="sale.md#0xcafe_sale_ClaimTicket">sale::ClaimTicket</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>purchase_tickets: <a href="_Table">table::Table</a>&lt;<a href="sale.md#0xcafe_sale_SaleId">sale::SaleId</a>, <a href="sale.md#0xcafe_sale_PurchaseTicket">sale::PurchaseTicket</a>&gt;</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_ClaimTicket"></a>

## Struct `ClaimTicket`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_ClaimTicket">ClaimTicket</a> <b>has</b> store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>claimed_amount: u64</code>
</dt>
<dd>

</dd>
<dt>
<code>tge_claimed: bool</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_sale_PurchaseTicket"></a>

## Struct `PurchaseTicket`



<pre><code><b>struct</b> <a href="sale.md#0xcafe_sale_PurchaseTicket">PurchaseTicket</a> <b>has</b> store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>purchased_amount: u64</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="@Constants_0"></a>

## Constants


<a name="0xcafe_sale_CLAIMING"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_CLAIMING">CLAIMING</a>: u64 = 5;
</code></pre>



<a name="0xcafe_sale_E_BAD_REQUEST"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_BAD_REQUEST">E_BAD_REQUEST</a>: u64 = 16;
</code></pre>



<a name="0xcafe_sale_E_CANT_END_SALE"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_CANT_END_SALE">E_CANT_END_SALE</a>: u64 = 13;
</code></pre>



<a name="0xcafe_sale_E_EXCEED_HARDCAP"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_EXCEED_HARDCAP">E_EXCEED_HARDCAP</a>: u64 = 7;
</code></pre>



<a name="0xcafe_sale_E_INVALID_SOFTCAP"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_INVALID_SOFTCAP">E_INVALID_SOFTCAP</a>: u64 = 1;
</code></pre>



<a name="0xcafe_sale_E_NOTHING_TO_CLAIM"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_NOTHING_TO_CLAIM">E_NOTHING_TO_CLAIM</a>: u64 = 11;
</code></pre>



<a name="0xcafe_sale_E_NOT_CREATOR"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_NOT_CREATOR">E_NOT_CREATOR</a>: u64 = 12;
</code></pre>



<a name="0xcafe_sale_E_NOT_IN_WL_TIME"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_NOT_IN_WL_TIME">E_NOT_IN_WL_TIME</a>: u64 = 14;
</code></pre>



<a name="0xcafe_sale_E_NOT_OWNER"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_NOT_OWNER">E_NOT_OWNER</a>: u64 = 15;
</code></pre>



<a name="0xcafe_sale_E_NOT_WHITELISTED"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_NOT_WHITELISTED">E_NOT_WHITELISTED</a>: u64 = 5;
</code></pre>



<a name="0xcafe_sale_E_NOT_WHITELIST_MODE"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_NOT_WHITELIST_MODE">E_NOT_WHITELIST_MODE</a>: u64 = 4;
</code></pre>



<a name="0xcafe_sale_E_SALE_EXISTS"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_SALE_EXISTS">E_SALE_EXISTS</a>: u64 = 0;
</code></pre>



<a name="0xcafe_sale_E_SALE_NOT_CLAIMING"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_SALE_NOT_CLAIMING">E_SALE_NOT_CLAIMING</a>: u64 = 9;
</code></pre>



<a name="0xcafe_sale_E_SALE_NOT_EXISTS"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_SALE_NOT_EXISTS">E_SALE_NOT_EXISTS</a>: u64 = 6;
</code></pre>



<a name="0xcafe_sale_E_SALE_NOT_FAIL"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_SALE_NOT_FAIL">E_SALE_NOT_FAIL</a>: u64 = 10;
</code></pre>



<a name="0xcafe_sale_E_SALE_NOT_SUCCESS"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_SALE_NOT_SUCCESS">E_SALE_NOT_SUCCESS</a>: u64 = 8;
</code></pre>



<a name="0xcafe_sale_E_START_TIME_LESS_THAN_END_TIME"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_START_TIME_LESS_THAN_END_TIME">E_START_TIME_LESS_THAN_END_TIME</a>: u64 = 2;
</code></pre>



<a name="0xcafe_sale_E_WHITELIST_TIME_INVALID"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_E_WHITELIST_TIME_INVALID">E_WHITELIST_TIME_INVALID</a>: u64 = 3;
</code></pre>



<a name="0xcafe_sale_FAIL"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_FAIL">FAIL</a>: u64 = 3;
</code></pre>



<a name="0xcafe_sale_FILLED"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_FILLED">FILLED</a>: u64 = 2;
</code></pre>



<a name="0xcafe_sale_RUNNING"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_RUNNING">RUNNING</a>: u64 = 1;
</code></pre>



<a name="0xcafe_sale_SUCCESS"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_SUCCESS">SUCCESS</a>: u64 = 4;
</code></pre>



<a name="0xcafe_sale_UPCOMING"></a>



<pre><code><b>const</b> <a href="sale.md#0xcafe_sale_UPCOMING">UPCOMING</a>: u64 = 0;
</code></pre>

