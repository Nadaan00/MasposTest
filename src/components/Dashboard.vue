<template>
  <v-main>
    <v-app>
      <div class="navbar ms-0">
        <div style="box-shadow: none; background-color: white; display: flex; width: 100%; flex-direction: column;">
          <div style="display: flex; align-items: center; width: 100%;">
            <div style="color: #1843c3; font-size: 24px; font-weight: bold;">MASPOS</div>
            <div style="flex-grow: 1;"></div>
            <v-btn class="mx-2" @click="tambahKategori" style="background-color: #1843c3; color: white;" @mouseover="hoverButton" @mouseleave="leaveButton">
              Tambah Kategori
            </v-btn>
            <v-btn class="mx-2" @click="tambahProduk" style="background-color: #1843c3; color: white;" @mouseover="hoverButton" @mouseleave="leaveButton">
              Tambah Produk
            </v-btn>
            <v-btn class="mx-2" icon @click="goToCart" style="color: #1843c3;">
              <v-icon>mdi-cart</v-icon>
            </v-btn>
            <v-btn class="mx-2" icon @click="logout" style="color: #1843c3;">
              <v-icon>mdi-logout</v-icon>
            </v-btn>
          </div>
          <hr style="width: 95%; border: 1px solid #ccc; margin: 1.5% auto 0;">
          <div style="display: flex; justify-content: center; gap: 16px; margin: 16px auto;">
            <v-btn @click="showAll" style="background-color: #1843c3; color: white;">
              Semua
            </v-btn>
            <v-btn @click="showActive" style="background-color: #1843c3; color: white;">
              Aktif
            </v-btn>
            <v-btn @click="showInactive" style="background-color: #1843c3; color: white;">
              Tidak Aktif
            </v-btn>
          </div>
        </div>
      </div>
      <!-- Main content goes here -->
    </v-app>
  </v-main>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          { title: 'Dashboard', icon: 'mdi-view-dashboard' },
          { title: 'Photos', icon: 'mdi-image' },
          { title: 'About', icon: 'mdi-help-box' },
        ],
        username:this.$route.params.username
      }
    },
    methods: {
      logout() {
        this.$router.replace({name:'login'})
      },
      tambahKategori() {
        // Add your logic for adding a category here
      },
      tambahProduk() {
        // Add your logic for adding a product here
      },
      goToCart() {
        // Add your logic for navigating to the cart here
      },
      hoverButton(event) {
        event.target.style.backgroundColor = '#2C59E5';
      },
      leaveButton(event) {
        event.target.style.backgroundColor = '#1843c3';
      },
      showAll() {
        // Add your logic for showing all items here
        console.log('Showing all items');
      },
      showActive() {
        // Add your logic for showing active items here
        console.log('Showing active items');
      },
      showInactive() {
        // Add your logic for showing inactive items here
        console.log('Showing inactive items');
      }
    }
  }
</script>