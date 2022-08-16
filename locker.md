
<a name="0xcafe_lock"></a>

# Module `0xcafe::lock`



-  [Struct `Lock`](#0xcafe_lock_Lock)
-  [Resource `LockStore`](#0xcafe_lock_LockStore)
-  [Constants](#@Constants_0)
-  [Function `create_lock`](#0xcafe_lock_create_lock)
-  [Function `claim`](#0xcafe_lock_claim)
-  [Function `is_exist_lock`](#0xcafe_lock_is_exist_lock)
-  [Function `get_lock_info`](#0xcafe_lock_get_lock_info)


<pre><code><b>use</b> <a href="">0x1::coin</a>;
<b>use</b> <a href="">0x1::error</a>;
<b>use</b> <a href="">0x1::signer</a>;
<b>use</b> <a href="">0x1::string</a>;
<b>use</b> <a href="">0x1::table</a>;
</code></pre>



<a name="0xcafe_lock_Lock"></a>

## Struct `Lock`



<pre><code><b>struct</b> <a href="locker.md#0xcafe_lock_Lock">Lock</a> <b>has</b> <b>copy</b>, drop, store
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>creator: <b>address</b></code>
</dt>
<dd>

</dd>
<dt>
<code>name: <a href="_String">string::String</a></code>
</dt>
<dd>

</dd>
<dt>
<code>end_time: u64</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="0xcafe_lock_LockStore"></a>

## Resource `LockStore`



<pre><code><b>struct</b> <a href="locker.md#0xcafe_lock_LockStore">LockStore</a>&lt;CoinType&gt; <b>has</b> key
</code></pre>



<details>
<summary>Fields</summary>


<dl>
<dt>
<code>locks: <a href="_Table">table::Table</a>&lt;<a href="_String">string::String</a>, <a href="locker.md#0xcafe_lock_Lock">lock::Lock</a>&gt;</code>
</dt>
<dd>

</dd>
<dt>
<code><a href="">coins</a>: <a href="_Table">table::Table</a>&lt;<a href="locker.md#0xcafe_lock_Lock">lock::Lock</a>, <a href="_Coin">coin::Coin</a>&lt;CoinType&gt;&gt;</code>
</dt>
<dd>

</dd>
</dl>


</details>

<a name="@Constants_0"></a>

## Constants


<a name="0xcafe_lock_ELOCK_AUTHORITY"></a>



<pre><code><b>const</b> <a href="locker.md#0xcafe_lock_ELOCK_AUTHORITY">ELOCK_AUTHORITY</a>: u64 = 2;
</code></pre>



<a name="0xcafe_lock_ELOCK_EXISTS"></a>



<pre><code><b>const</b> <a href="locker.md#0xcafe_lock_ELOCK_EXISTS">ELOCK_EXISTS</a>: u64 = 1;
</code></pre>



<a name="0xcafe_lock_ENO_LOCK"></a>



<pre><code><b>const</b> <a href="locker.md#0xcafe_lock_ENO_LOCK">ENO_LOCK</a>: u64 = 0;
</code></pre>
