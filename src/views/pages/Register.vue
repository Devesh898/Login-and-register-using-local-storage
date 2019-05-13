<template>
  <div class="app flex-row align-items-center">
    <div class="container">
      <b-row class="justify-content-center">
        <b-col md="6" sm="8">
          <b-card no-body class="mx-4">
            <b-card-body class="p-4">
              <form @submit.prevent="validateBeforeSubmit">
                <h1>Register</h1>
                <p class="text-muted">Create your account</p>
                <b-input-group class="mb-3">
                  <b-input-group-prepend>
                    <b-input-group-text><i class="icon-user"></i></b-input-group-text>
                  </b-input-group-prepend>
                  <b-form-input type="text" class="form-control" v-model="user.Username"  placeholder="Username" autocomplete="username" />
                </b-input-group>

                <b-input-group class="mb-3">
                  <b-input-group-prepend>
                    <b-input-group-text>@</b-input-group-text>
                  </b-input-group-prepend>
                  <b-form-input type="text" class="form-control" v-model="user.Email"  placeholder="Email" autocomplete="email" />
                </b-input-group>

                <b-input-group class="mb-3">
                  <b-input-group-prepend>
                    <b-input-group-text><i class="icon-lock"></i></b-input-group-text>
                  </b-input-group-prepend>
                  <b-form-input type="password" class="form-control" v-model="user.Password"  placeholder="Password" autocomplete="new-password" />
                </b-input-group>

                <b-input-group class="mb-4">
                  <b-input-group-prepend>
                    <b-input-group-text><i class="icon-lock"></i></b-input-group-text>
                  </b-input-group-prepend>
                  <b-form-input type="password" class="form-control" v-model="user.RepeatPassword"  placeholder="Repeat password" autocomplete="new-password" />
                </b-input-group>

                <input variant="success" name="register" type="submit" class="btn btn-primary" value="Create Account">
              </form>
            </b-card-body>
            <b-card-footer class="p-4">
              <b-row>
                <b-col cols="6">
                  <b-button block class="btn btn-facebook"><span>facebook</span></b-button>
                </b-col>
                <b-col cols="6">
                  <b-button block class="btn btn-twitter" type="button"><span>twitter</span></b-button>
                </b-col>
              </b-row>
            </b-card-footer>
          </b-card>
        </b-col>
      </b-row>
    </div>
  </div>
</template>


<script>

export default {
  
  name: 'Register',
    data () {
        return {
            user: {
                Username:'',
                Email:'',
                Password:'',
                RepeatPassword:'',
                
            },
            
           Registerr:[]
        }
    },
 
    methods: {
      
    validateBeforeSubmit(){
      const STORAGE_kEY="abcd"
      this.Registerr.push({
                Username:this.user.Username,
                Email:this.user.Email,
                Password:this.user.Password,
                RepeatPassword:this.user.RepeatPassword,

      })
              
      console.log(this.Registerr)
              
                localStorage.setItem(STORAGE_kEY,JSON.stringify(this.Registerr))
                
  
    },
    create(){
this.user=JSON.stringify(localStorage.getItem(STORAGE_kEY || []))
    }
    } 
}
</script>