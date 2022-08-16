
<a name="0xcafe_whitelist"></a>

# Module `0xcafe::whitelist`



-  [Struct `AddWhiteListCapability`](#0xcafe_whitelist_AddWhiteListCapability)
-  [Struct `WhiteListCapability`](#0xcafe_whitelist_WhiteListCapability)
-  [Resource `WhiteListTicket`](#0xcafe_whitelist_WhiteListTicket)
-  [Resource `AddWhitelistStore`](#0xcafe_whitelist_AddWhitelistStore)
-  [Constants](#@Constants_0)
-  [Function `grant_whitelist_role`](#0xcafe_whitelist_grant_whitelist_role)
-  [Function `register_whitelist`](#0xcafe_whitelist_register_whitelist)
-  [Function `is_account_whitelisted_raw`](#0xcafe_whitelist_is_account_whitelisted_raw)
-  [Function `add_whitelist`](#0xcafe_whitelist_add_whitelist)
-  [Function `remove_single_whitelist`](#0xcafe_whitelist_remove_single_whitelist)
-  [Function `remove_whitelist`](#0xcafe_whitelist_remove_whitelist)
-  [Function `is_account_registered_whitelist`](#0xcafe_whitelist_is_account_registered_whitelist)


<pre><code><b>use</b> <a href="">0x1::error</a>;
<b>use</b> <a href="">0x1::signer</a>;
<b>use</b> <a href="">0x1::table</a>;
</code></pre>



<a name="0xcafe_whitelist_AddWhiteListCapability"></a>

## Struct `AddWhiteListCapability`



<pre><code><b>struct</b> <a href="whitelist.md#0xcafe_whitelist_AddWhiteListCapability">AddWhiteListCapability</a> <b>has</b> store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>can_add_whitelist: bool</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_whitelist_WhiteListCapability"></a>

## Struct `WhiteListCapability`



<pre><code><b>struct</b> <a href="whitelist.md#0xcafe_whitelist_WhiteListCapability">WhiteListCapability</a> <b>has</b> drop, store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code><a href="whitelist.md#0xcafe_whitelist">whitelist</a>: bool</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_whitelist_WhiteListTicket"></a>

## Resource `WhiteListTicket`



<pre><code><b>struct</b> <a href="whitelist.md#0xcafe_whitelist_WhiteListTicket">WhiteListTicket</a>&lt;S_ID: <b>copy</b>, drop&gt; <b>has</b> key
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>whitelisted: <a href="_Table">table::Table</a>&lt;S_ID, <a href="whitelist.md#0xcafe_whitelist_WhiteListCapability">whitelist::WhiteListCapability</a>&gt;</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_whitelist_AddWhitelistStore"></a>

## Resource `AddWhitelistStore`



<pre><code><b>struct</b> <a href="whitelist.md#0xcafe_whitelist_AddWhitelistStore">AddWhitelistStore</a>&lt;S_ID: <b>copy</b>, drop&gt; <b>has</b> key
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>add_whitelist_capabilities: <a href="_Table">table::Table</a>&lt;S_ID, <a href="whitelist.md#0xcafe_whitelist_AddWhiteListCapability">whitelist::AddWhiteListCapability</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code>whitelisted: <a href="_Table">table::Table</a>&lt;S_ID, <a href="">vector</a>&lt;<b>address</b>&gt;&gt;</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="@Constants_0"></a>

## Constants


<a name="0xcafe_whitelist_E_NOT_HAVE_ADD_WHITELIST_CAPABILITY"></a>



<pre><code><b>const</b> <a href="whitelist.md#0xcafe_whitelist_E_NOT_HAVE_ADD_WHITELIST_CAPABILITY">E_NOT_HAVE_ADD_WHITELIST_CAPABILITY</a>: u64 = 2;
</code></pre>



<a name="0xcafe_whitelist_E_NOT_HAVE_WHITELIST_TICKET"></a>



<pre><code><b>const</b> <a href="whitelist.md#0xcafe_whitelist_E_NOT_HAVE_WHITELIST_TICKET">E_NOT_HAVE_WHITELIST_TICKET</a>: u64 = 3;
</code></pre>



<a name="0xcafe_whitelist_E_TOO_MUCH_ADDRESS"></a>



<pre><code><b>const</b> <a href="whitelist.md#0xcafe_whitelist_E_TOO_MUCH_ADDRESS">E_TOO_MUCH_ADDRESS</a>: u64 = 4;
</code></pre>



<a name="0xcafe_whitelist_E_WHITELIST_STORE_EXISTS"></a>



<pre><code><b>const</b> <a href="whitelist.md#0xcafe_whitelist_E_WHITELIST_STORE_EXISTS">E_WHITELIST_STORE_EXISTS</a>: u64 = 0;
</code></pre>



<a name="0xcafe_whitelist_E_WHITELIST_STORE_NOT_EXISTS"></a>



<pre><code><b>const</b> <a href="whitelist.md#0xcafe_whitelist_E_WHITELIST_STORE_NOT_EXISTS">E_WHITELIST_STORE_NOT_EXISTS</a>: u64 = 1;
</code></pre>
