<template>
  <div>
    <section style="position: relative;">
      <img class="img" src="@/assets/Canvas.svg" alt srcset />
      <div class="img-text">
        <div class="title">Keep Me Informed!</div>
        <div class="subtitle">Your Artist. Your Experience. Your Piece</div>
      </div>
    </section>
    <section class="register-panel mt-n2">
      <v-container>
        <div class="mx-auto" style="max-width:1086px">
          <div class="d-flex align-center justify-center mb-6 mb-md-16">
            <img class="right-arrow" src="@/assets/point.png" alt />
            <span class="register-hint">Curious? We will send you regularly updates:</span>
          </div>
          <div class="d-flex px-4 justify-space-between mb-4 mb-md-8">
            <div class="d-flex align-center">
              <img src="@/assets/headphones.png" alt />
              <span class="font-base ml-2 ml-sm-4 ml-md-12 white--text">
                News around the
                <span class="primary-text">Roadmap</span>
              </span>
            </div>
            <div class="d-flex ml-n3 align-center">
              <img src="@/assets/headphones.png" alt />
              <span class="font-base ml-2 ml-sm-4 ml-md-12 mr-2 white--text">
                Invites to
                <span class="primary-text">Our Beta</span>
              </span>
            </div>
          </div>
          <div class="d-flex px-4 justify-space-between mb-4 mb-md-8">
            <div class="d-flex align-center">
              <img src="@/assets/headphones.png" alt />
              <span class="font-base ml-2 ml-sm-4 ml-md-12 white--text">
                New
                <span class="primary-text">Features</span>
              </span>
            </div>
            <div class="d-flex align-center">
              <img src="@/assets/headphones.png" alt />
              <span class="font-base ml-2 ml-sm-4 ml-md-12 white--text">
                Upcoming
                <span class="primary-text">Specials</span>
              </span>
            </div>
          </div>
        </div>
        <!-- <v-row class="justify-center">
          <v-col cols="12" md="5">
            <div class="d-flex align-center">
              <img src="@/assets/headphones.png" alt />
              <span class="font-base ml-2 ml-sm-4 ml-md-12">News around the Roadmap</span>
            </div>
          </v-col>
          <v-col cols="12" md="5">
            <div class="d-flex align-center">
              <img src="@/assets/headphones.png" alt />
              <span class="font-base ml-2 ml-sm-4 ml-md-12">Invites to Our Beta</span>
            </div>
          </v-col>
          <v-col cols="12" md="5">
            <div class="d-flex align-center">
              <img src="@/assets/headphones.png" alt />
              <span class="font-base ml-2 ml-sm-4 ml-md-12">New Features</span>
            </div>
          </v-col>
          <v-col cols="12" md="5">
            <div class="d-flex align-center">
              <img src="@/assets/headphones.png" alt />
              <span class="font-base ml-2 ml-sm-4 ml-md-12">Upcoming Specials</span>
            </div>
          </v-col>
        </v-row>-->
        <div class="text-center mt-8 mt-md-16">
          <v-form class="px-2" ref="registerForm" @submit.prevent="onRegister">
            <v-text-field
              class="mb-5 mx-auto register-field"
              hide-details="auto"
              dense
              v-model="register.firstName"
              dark
              :rules="[v => !!v || 'First Name is required']"
              label="First Name"
              outlined
            ></v-text-field>
            <v-text-field
              class="mb-5 mx-auto register-field"
              hide-details="auto"
              dense
              dark
              v-model="register.lastName"
              :rules="[v => !!v || 'Last Name is required']"
              label="Last Name"
              outlined
              color="#FFFFFF"
            ></v-text-field>
            <v-text-field
              class="mb-5 mx-auto register-field"
              hide-details="auto"
              dense
              dark
              :rules="[v => !!v || 'Email is required']"
              v-model="register.email"
              label="Email"
              outlined
            ></v-text-field>
            <div class="d-flex justify-center">
              <v-checkbox
                v-model="isAccept"
                label="Accept the Terms and Conditions & Privacy Policy"
                color="#EED179"
                dark
                class="mx-auto"
                :class="$vuetify.breakpoint.lgAndUp? 'checkbox':''"
                background-color="transparent"
                hide-details
              ></v-checkbox>
            </div>
            <v-btn
              class="mt-5 mb-4 mt-md-13 mb-md-11 register-btn"
              :block="$vuetify.breakpoint.smAndDown"
              type="submit"
              :class="$vuetify.breakpoint.mdAndUp? 'register-btn-width':''"
              rounded
            >Register</v-btn>
          </v-form>
          <div class="text-center white--text text-h6 font-weight-normal">Or</div>
          <div class="discord mx-auto">
            <img class="logo" contain src="@/assets/discord.png" />
            <span class="text">Join our Discord Server</span>
          </div>
        </div>
      </v-container>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Home',

  data: () => ({
    register: {
      firstName: '',
      lastName: '',
      email: '',
    },
    isAccept: true,
    nameRules: [
      v => !!v || 'Name is required',
    ],
  }),
  methods: {
    onRegister() {
      if (this.$refs.registerForm.validate()) {
        console.log('validate');
      }
    }
  }
}
</script>

<style lang="scss">
$primary-text-color: #EED179;
.primary-text{
  color:#EED179;
}
  .img{
    width: 100%;
    object-fit: contain;
    
  }
  .font-base{
    font-size:29px
  }
.img-text{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
   .title{
     font-size: 5rem !important;
     color: $primary-text-color;
     line-height: 100px;
   }
   .subtitle{
     color: #ffffff;
     font-size: 3.25rem;
   }
}
.register-panel{
  background-color: #350045;
  padding-top: 150px;
  padding-bottom: 175px;
  img{
    width: 95px!important;
  }
  .right-arrow{
    margin-right: 94px;
  }
  .register-hint{
    color: $primary-text-color;
    font-size: 45px;
  }
}
.register-field{
  max-width: 926px !important;
}

.register-field.v-input .v-input__slot {
	border-radius: 8px;
}
.register-field.v-text-field--outlined fieldset {
    color: #EED179 !important;
}
.register-field.v-text-field--outlined.v-input--dense .v-label {
	color: #FFFFFF !important;
  opacity: 50%;
}
.checkbox .v-icon{
  font-size: 33px !important;
}
.checkbox .v-label{ 
  font-size: 29px !important;
  margin-left: 30px !important;
}
.register-btn{
  background: linear-gradient(#D5AA32, #EED179);
}
.register-btn-width{
  width: 545px !important;
 
}
.discord{
  display: flex;
  align-items: center;
  max-width: 600px;
  justify-content: space-between;
  .logo{
    width: 67px!important;
    
  }
  .text{
    font-size: 45px;
    color: $primary-text-color;
  }
}
@media screen and (max-width: 960px) {
    .font-base{
    font-size:1rem
  }
  .img-text{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    .title{
      font-size: 1.5rem !important;
      color: $primary-text-color;
      line-height: 2rem;
    }
    .subtitle{
      color: #ffffff;
      font-size: 1rem;
    }
  }
  .discord{
  display: flex;
  align-items: center;
  max-width: 600px;
  justify-content: center;
  .logo{
    width: 42px!important;
    margin-right: 1rem;
    
  }
  .text{
    font-size: 1.75rem;
    color: $primary-text-color;
  }
}
  .register-panel{
  background-color: #350045;
  padding-top: 25px;
  padding-bottom: 35px;
  img{
    width: 28px!important;
  }
  .right-arrow{
    margin-right: 8px;
  }
  .register-hint{
    color: $primary-text-color;
    font-size:1rem;
  }
}
}
@media screen and (max-width: 460px) {
  .font-base{
    font-size:.75rem
  }
  .register-panel{
      background-color: #350045;
      padding-top: 25px;
      padding-bottom: 35px;
      img{
        width: 28px!important;
      }
      .right-arrow{
        margin-right: 8px;
      }
      .register-hint{
        color: $primary-text-color;
        font-size:.75rem;
    }
}
   .discord{
  display: flex;
  align-items: center;
  max-width: 600px;
  justify-content: center;
  .logo{
    width: 32px!important;
    margin-right: 1rem;
    
  }
  .text{
    font-size: 1.25rem;
    color: $primary-text-color;
  }
}
}
</style>

