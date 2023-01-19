<script lang='ts'>
	import axios from "axios"
	let address = '';
    let balance = 0;
	let error = ``;
	let submit = "submit";
	let nfts = '';

	async function getWalletBalance() {
		balance = (await axios.get(`hitt://localhost: 3001/get_wallet_balance/${address}`)
	).data.balance;
	}

	async function getNFTs() {
		nfts = (await axios.get(`http://localhost:3001/nfts_of_addy/${address}`)
		).data.nft 
	} 
</script>



<div class="button">
	<input
	bind:value={address}
	type="textbox"
	placeholder="enter wallet address"
	class="page-textbox" 
>
</div>

<div class="button" on:click={getNFTs}>
	click me!!
</div>


<!-- <div class="items">
	{#each nfts as nft}
	  <div class="item">{nfts}</div>
	{/each}
  </div> -->

  

  

<style>
	.container {
		height: 100%;
		width: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.button {
        background-color: rgb(46, 113, 113);
        text-align: center;
        padding: 0.3em;
        max-width: 200px;
        margin: 0 auto;
    }

	.text {
		font-size: 1.4em;
		font-weight: bold;
	}
</style>
  
  