<template>
  <v-app>
    <v-main>
      <v-container fluid class="full-screen">
        <v-row class="full-screen">
          <v-col cols="12" md="6">
            <div class="banner">
              <!-- <v-img src="@/assets/images/banner.jpg" class="fill-height"></v-img> -->
            </div>
          </v-col>
          <v-col cols="12" md="6">
            <h2>MASPOS</h2>
            <v-layout align-center justify-center>
              <v-flex xs12 sm8 md10>
                <v-card-text class="py-4 mt-5 ms-5">
                  <h4>Selamat Datang di MASPOS</h4>
                  <p>Masuk untuk mengelola bisnis Anda dengan mudah dan efisien. MASPOS menghadirkan solusi point-of-sale terbaik untuk memudahkan operasional sehari-hari</p>
                  <form ref="form" @submit.prevent="isRegister ? register() : login()">
                    <div class="input-label mb-2">Username</div>
                    <v-text-field
                      v-model="username"
                      name="username"
                      type="text"
                      required
                      outlined
                      dense
                    ></v-text-field>
                    <div class="input-label mb-2">Password</div>
                    <v-text-field
                      v-model="password"
                      name="password"
                      type="password"
                      required
                      outlined
                      dense
                    ></v-text-field>
                    <div v-if="isRegister" class="input-label mb-2">Konfirmasi Password</div>
                    <v-text-field v-if="isRegister"
                      v-model="confirmPassword"
                      name="confirmPassword"
                      type="password"
                      required
                      outlined
                      dense
                    ></v-text-field>
                    <div class="red--text">{{ errorMessage }}</div>
                    <v-btn type="submit" class="mt-4 btn-hover" color="#1843C3" value="log in" block dark>{{ isRegister ? stateObj.register.name : stateObj.login.name }}</v-btn>
                    <v-btn class="mt-4" color="#1843C3" block dark @click="isRegister = !isRegister;">
                      {{ toggleMessage }}
                    </v-btn>
                  </form>
                </v-card-text>
              </v-flex>
            </v-layout>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      username: "",
      password: "",
      confirmPassword: "",
      isRegister: false,
      errorMessage: "",
      stateObj: {
        register: {
          name: 'Register',
          message: 'Already have an account? Login.'
        },
        login: {
          name: 'Login',
          message: 'Register'
        }
      }
    };
  },
  methods: {
    login() {
      const { username } = this;
      this.$router.replace({ name: "dashboard", params: { username: username } });
    },
    register() {
      if (this.password === this.confirmPassword) {
        this.isRegister = false;
        this.errorMessage = "";
        this.$refs.form.reset();
      } else {
        this.errorMessage = "Password did not match";
      }
    }
  },
  computed: {
    toggleMessage() {
      return this.isRegister ? this.stateObj.register.message : this.stateObj.login.message;
    }
  }
};
</script>

<style scoped>
h2 {
  display: flex;
  justify-content: flex-end; 
  padding: 16px;
  margin: 0;
  color: #1843C3;
}

.input-label {
  font-weight: bold;
  color: #333;
}

html, body, #app, .v-application {
  height: 100%;
  overflow: hidden;
}

.btn-hover:hover {
  background-color: #2C59E5 !important;
}

.toggle-text {
  color: #1843C3;
  cursor: pointer;
  text-decoration: underline;
}

.banner {
  background-color: #1843C3;
  height: 100%;
  border-radius: 20px;
}

.full-screen {
  height: 95vh;
  /* width: 100vw; */
}
</style>