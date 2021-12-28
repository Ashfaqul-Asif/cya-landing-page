<template>
  <div>
    <section style="position: relative;">
      <img class="img" src="@/assets/DJ.png" alt srcset />
      <div class="img-text">
        <div class="text title">How Can I Join as an Artist?</div>
        <div class="subtitle">Play. Earn. Enjoy</div>
      </div>
    </section>
    <section class="mt-n2" style="background-color:#350045">
      <v-container>
        <img class="img" src="@/assets/order.png" alt srcset />
      </v-container>
    </section>
    <section class="register-panel-2 mt-n2">
      <v-container>
        <div class="mx-auto" style="max-width:1086px">
          <div class="d-flex align-center justify-center mb-10">
            <img class="right-arrow" src="@/assets/point.png" alt />
            <span class="register-hint">ARTISTS Contact Information</span>
          </div>
          <span
            class="white--text font-base text-center"
          >Please enter the following information - We will get back in touch with you ASAP!</span>
        </div>

        <div class="text-center mt-16">
          <v-form class="px-2" ref="registerForm" @submit.prevent="onRegister">
            <v-row>
              <v-col cols="12" md="6">
                <v-text-field
                  class="register-field"
                  hide-details="auto"
                  dense
                  v-model="register.artistName"
                  dark
                  :rules="[v => !!v || 'Artist Name is required']"
                  label="Artist Name"
                  outlined
                ></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field
                  class="register-field"
                  hide-details="auto"
                  dense
                  v-model="register.genre"
                  dark
                  :rules="[v => !!v || 'Genre is required']"
                  label="Genre"
                  outlined
                ></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field
                  class="register-field"
                  hide-details="auto"
                  dense
                  v-model="register.contactName"
                  dark
                  :rules="[v => !!v || 'Contact Name is required']"
                  label="Contact Name"
                  outlined
                ></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field
                  class="register-field"
                  hide-details="auto"
                  dense
                  v-model="register.socialMediaChannel"
                  dark
                  :rules="[v => !!v || 'Social media channel is required']"
                  label="Main Social Media Channel"
                  outlined
                ></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field
                  class="register-field"
                  hide-details="auto"
                  dense
                  v-model="register.email"
                  dark
                  :rules="[v => !!v || 'Email is required']"
                  label="Email"
                  outlined
                ></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field
                  class="register-field"
                  hide-details="auto"
                  dense
                  v-model="register.instaFollowers"
                  dark
                  :rules="[v => !!v || 'Insta followers is required']"
                  label="# Insta Followers"
                  outlined
                ></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field
                  class="register-field"
                  hide-details="auto"
                  dense
                  v-model="register.phoneNo"
                  dark
                  :rules="[v => !!v || 'Phone no is required']"
                  label="Phone No.contact"
                  outlined
                ></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field
                  class="register-field"
                  hide-details="auto"
                  dense
                  v-model="register.spotifyFollowers"
                  dark
                  :rules="[v => !!v || 'Spotify followers is required']"
                  label="# Spotify Followers"
                  outlined
                ></v-text-field>
              </v-col>
            </v-row>
            <!-- <v-text-field
              class="mb-5 mx-auto"
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
              class="mb-5 mx-auto"
              hide-details="auto"
              dense
              dark
              :rules="[v => !!v || 'Email is required']"
              v-model="register.email"
              label="Email"
              outlined
            ></v-text-field>-->
            <div class="d-flex justify-center mt-8">
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
              class="mt-13 mb-11 register-btn"
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
  name: 'landing-2',

  data: () => ({
    register: {
      artistName: '',
      genre: '',
      contactName: '',
      socialMediaChannel: '',
      email: '',
      instaFollowers: '',
      spotifyFollowers: '',
      phoneNo: '',

    },
    isAccept: true,

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
.register-panel-2{
  background-color: #350045;
  padding-top: 75px;
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

</style>

