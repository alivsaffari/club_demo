<script setup lang="ts">
const club_name = defineModel('club_name')
const tonConnectUI = new TON_CONNECT_UI.TonConnectUI({
  manifestUrl: 'https://club-demo.vercel.app/tonconnect-manifest.json',
  buttonRootId: 'ton-connect'
})
tonConnectUI.uiOptions = {
  twaReturnUrl: 'https://t.me/token_cafe_bot/token_app'
}

async function connectToWallet() {
  const connectedWallet = await tonConnectUI.connectWallet()
  // Do something with connectedWallet if needed
  console.log(connectedWallet)
}

function call_wallet() {
  // Call the function
  connectToWallet().catch((error) => {
    console.error('Error connecting to wallet:', error)
  })
}
</script>

<template>
  <form class="establish_form" @submit="call_wallet">
    <h1>🏆</h1>
    <h1>Establish Your Club!</h1>
    <input
      type="text"
      class="form-control"
      id="club_name"
      v-model="club_name"
      placeholder="Club Name"
    />
    <button type="submit" class="btn btn-primary" id="ton-connect">Let's Start!</button>
  </form>
</template>

<style scoped>
.establish_form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
  height: 100vh;
}

input {
  max-width: 50%;
}
</style>
