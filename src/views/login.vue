<template>
  <div class="container-login">
    <div id="login">
      <!-- <h1>LOGIN</h1> -->
      <div class="login">
        <div class="inputs">
          <input type="text" name="username" v-model="input.username" placeholder="Username" />
           <span class="fas fa-user"></span>
        </div>
        <div class="inputs">   
          <input type="password" name="password" v-model="input.password" placeholder="Password" />
          <span class="fas fa-lock"></span>
        </div>
        <button type="button" v-on:click="login()">ENTRAR</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      input: {
        username: "",
        password: ""
      }
    };
  },
  methods: {
    login() {
      if (this.input.username != "" && this.input.password != "") {
        if (this.input.password == this.$parent.mockAccount.password) {
          this.$emit("authenticated", true);
          this.$router.replace({ name: "secure" });
        } else {
          alert("Dica de senha: ave oceânica");
        }
      }
    }
  }
};
</script>

<style lang="scss">
@import "./login.scss";
</style>