<template>
  <div>
    <WalletButton msg="The Multi Button"/>
    <CoinGame msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import WalletButton from './components/WalletButton.vue';
import CoinGame from './components/CoinGame.vue'
import {
  PhantomWalletAdapter
} from '@solana/wallet-adapter-wallets';
import { initWallet } from 'solana-wallets-vue';

export default {
  name: 'App',
  components: {
    WalletButton,
    CoinGame
  },
  setup() {
    console.log('Initializing wallet...');

    const walletOptions = {
      wallets: [
        new PhantomWalletAdapter()
      ],
      autoConnect: true,
    };

    initWallet(walletOptions);
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
