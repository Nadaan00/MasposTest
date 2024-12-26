<template>
  <v-app>
    <v-main>
      <div style="position: fixed; top: 20px; left: 50%; transform: translateX(-50%); width: 95vw; border: 1px solid #ccc; border-radius: 15px; padding-top: 16px; background-color: white; z-index: 1;">
        <div style="display: flex; align-items: center; background-color: white; box-shadow: none; padding: 8px 16px;">
          <div style="color: #1843c3; font-size: 24px; font-weight: bold;">MASPOS</div>
          <v-spacer></v-spacer>
          <v-btn class="mx-2" @click="tambahKategori" style="background-color: #1843c3; color: white; margin-right: 8px;" @mouseover="hoverButtonKategori" @mouseleave="leaveButtonKategori">
            Tambah Kategori
          </v-btn>
          <v-btn class="mx-2" @click="tambahProduk" style="background-color: #1843c3; color: white; margin-right: 8px;" @mouseover="hoverButtonProduk" @mouseleave="leaveButtonProduk">
            Tambah Produk
          </v-btn>
          <v-btn class="mx-2" icon @click="goToCart" style="color: #1843c3; margin-right: 8px;">
            <v-icon>mdi-cart</v-icon>
          </v-btn>
          <v-btn class="mx-2" icon @click="logout" style="color: #1843c3;">
            <v-icon>mdi-logout</v-icon>
          </v-btn>
        </div>
        <hr style="margin: 16px auto; border: none; border-top: 1px solid #ccc; width: 95%;">
        <div style="padding: 8px 0 16px 0;">
          <v-btn class="mx-2" @click="showAll" style="background-color: #1843c3; color: white;">
            Semua
          </v-btn>
          <v-btn class="mx-2" @click="showBurger" style="background-color: #aabcf4; color: #1843c3;">
            Burger
          </v-btn>
          <v-btn class="mx-2" @click="showPizza" style="background-color: #aabcf4; color: #1843c3;">
            Pizza
          </v-btn>
          <v-btn class="mx-2" @click="showDrink" style="background-color: #aabcf4; color: #1843c3;">
            Drink
          </v-btn>
        </div>
      </div>
      <div style="display: grid; grid-template-columns: repeat(5, 1fr); gap: 16px; margin-top: 180px; padding: 16px;">
        <v-card v-for="n in 10" :key="n">
          <v-img src="@/assets/banner.jpg" height="150px" width="210px" style="object-fit: cover; display: block; margin: 0 auto; margin-top: 12px;"></v-img>
          <v-card-title>Pepperoni Chesee</v-card-title>
          <v-card-text style="color: #008000;">
            Rp 45.000
          </v-card-text>
          <v-card-actions>
            <v-btn style="background-color: #1843c3; color: white; width: 100%;">Keranjang</v-btn>
          </v-card-actions>
        </v-card>
      </div>
      <!-- Main content goes here -->
    </v-main>
  </v-app>
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
        this.$router.push({ name: 'kategori' });
      },
      tambahProduk() {
        this.$router.push({ name: 'produk' });
      },
      goToCart() {
        // Add your logic for navigating to the cart here
      },
      showAll() {
        // Add your logic for showing all items here
        console.log('Showing all items');
      },
      showBurger() {
        // Add your logic for showing burger items here
        console.log('Showing burger items');
      },
      showPizza() {
        // Add your logic for showing pizza items here
        console.log('Showing pizza items');
      },
      showDrink() {
        // Add your logic for showing drink items here
        console.log('Showing drink items');
      }
    }
  }
</script>

