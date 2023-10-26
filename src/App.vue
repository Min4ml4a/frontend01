<template>
  
  <v-app style="color: #33cccc">
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
       

        <v-btn text @click="goToHome()"> Category </v-btn>
      </div>

      <v-spacer></v-spacer>

      

      <v-btn text @click="goToHome()"> หน้าเเรก </v-btn>

      <v-btn text @click="gotoHomepage()"> Category </v-btn>

      <v-btn text @click="goToManage()"> จัดการ Product </v-btn>

      <v-btn text @click="goToLogin()"> เข้าสู่ระบบ </v-btn>
    </v-app-bar>
    <v-main>
      <router-view />
    </v-main>
    
  
  </v-app>
  
</template>

<script>
export default {
  name: "App",

  data: () => ({}),
  methods: {
    goToHome() {
      this.$router.push("/");
    },
    goToLogin() {
      this.$router.push("/login");
    },
    goToManage() {
      this.$router.push("/EditDelete");
      // this.$router.push({path: })
    },
    goToRegister() {
      this.$router.push("/Register");
    },
    gotoHomepage() {
      this.$router.push("/Homepage");
    },
    gotoAdd() {
      this.$router.push("/add");
    },
  },
};
</script>
