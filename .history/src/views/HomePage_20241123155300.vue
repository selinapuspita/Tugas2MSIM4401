<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Cryptocurrency List</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <div class="container">
        <ion-button expand="block" @click="fetchCryptocurrencies" class="fetch-button">
          Get Data
        </ion-button>

        <div class="table-container">
          <table class="crypto-table">
            <thead>
              <tr>
                <th>Name</th>
                <th>Symbol</th>
                <th>Harga USD</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="crypto in cryptocurrencies" :key="crypto.id">
                <td>{{ crypto.name }}</td>
                <td>{{ crypto.symbol }}</td>
                <td>{{ parseFloat(crypto.price_usd).toFixed(2) }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>

<script>
import axios from "axios";

export default{
  data() {
    return{
      cryptocurrencies: [],
    };
  },
  methods: {
    fetchCryptocurrencies() {
      axios.get("https://api.coinlore.net/api/tickers/")
      .then((response) => {
        this.cryptocurrencies = response.data.data;
      })
      .catch((error) => {
        console.error(error);
      });
    },
  },
};
</script>

<style scoped>
  .container {
    padding: 16px;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .fetch-button {
    margin-bottom: 16px;
  }

  .table-container {
    overflow-x: auto;
    width: 100%;
  }

  .crypto-table {
    width: 100%;
    border-collapse: collapse;
    margin: 0 auto;
    font-size: 16px;
    text-align: center;
  }

  .crypto-table th, .crypto-table td {
    padding: 8px 12px;
    border:1px solid #ddd;
  }

  .crypto-table th {
    
  }
</style>
