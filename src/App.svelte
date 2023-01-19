<script lang='ts'>
	import axios from "axios"
	let address = '';
	let nfts = '';
    let balance = 0;
	let error = ``;
	let submit = "submit";

	async function getWalletBalance() {
		balance = (await axios.get(`hitt://localhost: 3001/get_wallet_balance/${address}`)
	).data.balance;
	}

	async function getNFTs() {
		nfts = (await axios.get(`http://localhost:3001/nfts_of_addy/${address}`)
		).data.nfts
	}
</script>




<div class="container">
	<div class="text"> 
		
	</div>

<div class="button">
	<input
	bind:value={address}
	type="textbox"
	placeholder="enter wallet address"
	class="page-textbox" 
>
</div>

<div class="text"> 
	<input	
	bind:value={getNFTs} 
>
	</div>
</div>


<input type="text" bind:value={address} />
  
  <div on:click={async() => {
    getNFTs = (await axios.get(`${YOUR_BACKEND_URL}/get_wallet_balance/${address}`)).data;
  }}>button text</div>
  
  <div>{balance.toFixed(2)} SOL</div>

<input type="text" bind:value={address} />
  
  <div on:click={async() => {
    balance = (await axios.get(`${YOUR_BACKEND_URL}/get_wallet_balance/${address}`)).data;
  }}>button text</div>
  
  <div>{balance.toFixed(2)} SOL</div>
  
  

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

<script lang="ts">
    const axios = require(`axios`);
    let  = ``;
    let balance = 0;
  </script>
  
  