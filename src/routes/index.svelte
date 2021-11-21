<script>
  import { onMount } from 'svelte'
  import * as nearAPI from 'near-api-js'
  let near;

  onMount(async() => {
    const config = {
      networkId: "testnet",
      nodeUrl: "https://rpc.testnet.near.org",
      walletUrl: "https://wallet.testnet.near.org",
      helperUrl: "https://helper.testnet.near.org",
      explorerUrl: "https://explorer.testnet.near.org",
      keyStore: new nearAPI.keyStores.BrowserLocalStorageKeyStore()
    };

    near = await nearAPI.connect(config);
  })
</script>

{JSON.stringify(near)}
