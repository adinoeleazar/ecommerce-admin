<template>
<div class="container login-container">
    <div class="col-sm login-form-2">
                    <h3>Register</h3>
                    <form @submit.prevent="register">
                        <div class="form-group">
                            <input v-model="username" type="text" class="form-control" placeholder="Your Username" value="" />
                        </div>
                        <div class="form-group">
                            <input v-model="email" type="text" class="form-control" placeholder="Your Email" value="" />
                        </div>
                        <div class="form-group">
                            <input v-model="password" type="password" class="form-control" placeholder="Your Password" value="" />
                        </div>
                        <div class="form-group">
                            <input type="submit" class="btnSubmit" value="Register" />
                        </div>
                        <div class="form-group">
                            <a href="#" class="ForgetPwd" value="Login">Already have an account? Click here to sign in</a>
                        </div>
                    </form>
    </div>
</div>
</template>

<script>

export default {
  name: 'Register',
  data () {
    return {
      username: '',
      email: '',
      password: ''
    }
  },
  methods: {
    register () {
      const userData = {
        username: this.username,
        email: this.email,
        password: this.password
      }
      this.$store.dispatch('register', userData)
    }
  }
}
</script>

<style>
.login-container{
    margin-top: 5%;
    margin-bottom: 5%;
}
.login-form-1{
    padding: 5%;
    box-shadow: 0 5px 8px 0 rgba(0, 0, 0, 0.2), 0 9px 26px 0 rgba(0, 0, 0, 0.19);
}
.login-form-1 h3{
    text-align: center;
    color: #333;
}
.login-form-2{
    padding: 5%;
    background: #0062cc;
    box-shadow: 0 5px 8px 0 rgba(0, 0, 0, 0.2), 0 9px 26px 0 rgba(0, 0, 0, 0.19);
}
.login-form-2 h3{
    text-align: center;
    color: #fff;
    font-size: 30pt
}
.login-container form{
    padding: 10%;
}
.btnSubmit
{
    width: 50%;
    border-radius: 1rem;
    padding: 1.5%;
    border: none;
    cursor: pointer;
}
.login-form-1 .btnSubmit{
    font-weight: 600;
    color: #fff;
    background-color: #0062cc;
}
.login-form-2 .btnSubmit{
    font-weight: 600;
    color: #0062cc;
    background-color: #fff;
}
.login-form-2 .ForgetPwd{
    color: #fff;
    font-weight: 600;
    text-decoration: none;
}
.login-form-1 .ForgetPwd{
    color: #0062cc;
    font-weight: 600;
    text-decoration: none;
}
</style>
