<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Cryptocurrency List</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <div class="container">
        <ion-button expand="block"
        @click="fetchCryptocurrencies"
        class="fetch-button">
        Get data  
      </ion-button>

      <div class="table-container">
        <table class="crypto-table">
          <thead>
            <tr>
              <th>Name</th>
              <th>Simbol</th>
              <th>Harga USD</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="crypto in cryptocurrencies":key="crypto.id">
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
</script>

<style scoped>

</style>
