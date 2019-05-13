<template>
  <div class="app flex-row align-items-center">
    <div class="container">
      <b-row class="justify-content-center">
        <b-col md="8">
          <b-card-group>
            <b-card no-body class="p-4">
              <b-card-body>
                <b-form Action="#" @submit.prevent="LoginAuth">
                  <h1>Login</h1>
                  <p class="text-muted">Sign In to your account</p>
                  <b-input-group class="mb-3">
                    <b-input-group-prepend><b-input-group-text><i class="icon-user"></i></b-input-group-text></b-input-group-prepend>
                    <b-form-input type="text" class="form-control" placeholder="Username" autocomplete="username email"  v-model="log.Uemail" />
                  </b-input-group>
                  <b-input-group class="mb-4">
                    <b-input-group-prepend><b-input-group-text><i class="icon-lock"></i></b-input-group-text></b-input-group-prepend>
                    <b-form-input type="password" class="form-control" placeholder="Password" autocomplete="current-password"  v-model="log.Upass"/>
                  </b-input-group>
                  <b-row>
                    <b-col cols="6">
                     <input type="submit" variant="primary" class="btn btn-primary" value="Login">
                    </b-col>
                    <b-col cols="6" class="text-right">
                      <b-button variant="link" class="px-0">Forgot password?</b-button>
                    </b-col>
                  </b-row>
                </b-form>
              </b-card-body>
            </b-card>
            <b-card no-body class="text-white bg-primary py-5 d-md-down-none" style="width:44%">
              <b-card-body class="text-center">
                <div>
                  <h2>Sign up</h2>
                  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
                  <router-link to="/register" class="btn btn-link"> <b-button variant="primary" class="active mt-3">Register Now!</b-button></router-link>
                  <router-link to="/register" class="btn btn-link">Register</router-link>
                
                </div>
              </b-card-body>
            </b-card>
          </b-card-group>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data(){
return {
  log:{
  Uemail:'',
  Upass:'',
  Login:[]
}}
  },
  
  
  methods:{
    LoginAuth(){
 var obj,email,password,x;
 
  obj=JSON.parse(localStorage.abcd)
 for(x in obj){
    email=obj[x]["Email"];
console.log(email)
    password=obj[x]["Password"];
console.log(password)
 if(email==this.log.Uemail && password==this.log.Upass)
    {

        console.log("success")
const STORAGE_kEY="abcde"
      this.log.Login.push({
                Email:this.log.Uemail,
                Password:this.log.UPass
      })
      localStorage.setItem(STORAGE_kEY,JSON.stringify(this.log.Login))
this.$router.push('*')
break;
    }
else{
  console.log("error")

}

 }
}, create(){
this.log=JSON.stringify(localStorage.getItem(STORAGE_kEY || []))}
 
 }}
</script>
