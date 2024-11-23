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

      <div>
      </div>

    </ion-content>
  </ion-page>
</template>

<script>
</script>

<style scoped>

</style>
