<script setup>
import AppLayout from '@/components/layout/AppLayout.vue';
</script>

<!-- prepend-icon="mdi-account" -->

<template>
  <AppLayout>
    <template #login_reg>
      <v-row align="center" justify="center">
        <v-col cols="12" sm="8" md="8">
          <v-card class="elevation-12 custom-border">
            <v-window v-model="step">
              <!-- First Window Item (Sign In) -->
              <v-window-item :value="-1">
                <v-row>
                  <!-- Left Side -->
                  <v-col cols="12" md="8">
                    <v-card-text class="mt-12 mx-7">
                      <h1 class="text-center display-2" style="color: rgba(176, 224, 230, 1);">Sign in to AeroCast</h1>
                      <div class="text-center mt-4 mb-8">
                        <v-icon class="mx-8">
                          <v-icon><i class="fa-brands fa-facebook" style="color: #05368a;"></i></v-icon>
                        </v-icon>
                        <v-icon class="me-8">
                          <v-icon><i class="fa-regular fa-envelope" style="color: #b52a12;"></i></v-icon>
                        </v-icon>
                        <v-icon>
                          <v-icon><i class="fa-brands fa-linkedin" style="color: #166bda;"></i></v-icon>
                        </v-icon>
                      </div>
                      <!-- <h4 class="text-center mt-4 mb-5">Ensure your email for registration</h4> -->
                      <v-form>
                        <v-text-field label="Email" name="Email" prepend-icon="mdi-email" type="text"
                          color="teal accent-3" />
                        <v-text-field id="password" label="Password" name="Password" prepend-icon="mdi-lock"
                          type="password" color="teal accent-3" />
                      </v-form>
                      <h3 class="text-center mt-3">Forgot password?</h3>
                    </v-card-text>
                    <div class="text-center mt-3 mb-10">
                      <v-btn rounded
                        style="background: linear-gradient(to bottom right, rgba(135, 206, 250, 1), rgba(176, 224, 230, 1));">SIGN
                        IN</v-btn>
                    </div>
                  </v-col>

                  <!-- Right Side -->
                  <v-col cols="12" md="4"
                    style="background: linear-gradient(to bottom right, rgba(135, 206, 250, 1), rgba(176, 224, 230, 1));">
                    <v-card-text class="white--text mt-12" style="color: #fff;">
                      <h1 class="text-center display-1">Welcome!</h1>
                      <h5 class="text-center">Enter your personal email and start your journey with us</h5>
                    </v-card-text>
                    <div class="text-center mb-12">
                      <v-btn rounded outlined="" dark @click="nextStep">SIGN UP</v-btn>
                    </div>
                  </v-col>
                </v-row>
              </v-window-item>

              <!-- Second Window Item (Sign Up) -->
              <v-window-item :value="2">
                <v-row class="full-height">
                  <!-- Left Side -->
                  <v-col cols="12" md="4"
                    style="background: linear-gradient(to bottom right, rgba(135, 206, 250, 1), rgba(176, 224, 230, 1));">
                    <v-card-text class="mt-12" style="color:#fff;">
                      <h1 class="text-center display-1">Welcome Back!</h1>
                      <h5 class="text-center">To keep connected with us please login with your personal info</h5>
                    </v-card-text>
                    <div class="text-center mb-5">
                      <v-btn rounded outlined="" dark @click="previousStep">SIGN IN</v-btn>
                    </div>
                  </v-col>

                  <!-- Right Side -->
                  <v-col cols="12" md="8">
                    <v-card-text class="mt-12 mx-">
                      <h1 class="text-center display-2" style="color: rgba(176, 224, 230, 1);">Create an Account</h1>
                      <div class="text-center mt-4 mb-8">
                        <v-icon class="mx-8">
                          <v-icon><i class="fa-brands fa-facebook" style="color: #05368a;"></i></v-icon>
                        </v-icon>
                        <v-icon class="me-8">
                          <v-icon><i class="fa-regular fa-envelope" style="color: #b52a12;"></i></v-icon>
                        </v-icon>
                        <v-icon>
                          <v-icon><i class="fa-brands fa-linkedin" style="color: #166bda;"></i></v-icon>
                        </v-icon>
                      </div>
                      <!-- <h4 class="text-center mt-4 mb-5">Ensure your email for registration</h4> -->
                      <v-form v-model="valid">
                        <v-container>
                          <v-row>
                            <!-- First Name and Last Name Side by Side -->
                            <v-col cols="12" md="6">
                              <v-text-field v-model="firstname" :counter="10" :rules="nameRules" label="First Name"
                                prepend-icon="mdi-account" required color="teal accent-3"></v-text-field>
                            </v-col>

                            <v-col cols="12" md="6">
                              <v-text-field v-model="lastname" :counter="10" :rules="nameRules" label="Last Name"
                              required color="teal accent-3"></v-text-field>
                            </v-col>
                          </v-row>

                          <!-- Email Field on New Line -->
                          <v-row>
                            <v-col cols="12">
                              <v-text-field v-model="email" label="Email" prepend-icon="mdi-email" type="text"
                                color="teal accent-3"></v-text-field>
                            </v-col>
                          </v-row>

                          <!-- Password Field on New Line -->
                          <v-row>
                            <v-col cols="12">
                              <v-text-field id="password" v-model="password" label="Password" prepend-icon="mdi-lock"
                                type="password" color="teal accent-3"></v-text-field>
                            </v-col>
                          </v-row>
                        </v-container>
                      </v-form>

                    </v-card-text>
                    <div class="text-center mt-3 mb-10">
                      <v-btn rounded
                        style="background: linear-gradient(to bottom right, rgba(135, 206, 250, 1), rgba(176, 224, 230, 1));">SIGN
                        UP</v-btn>
                    </div>
                  </v-col>
                </v-row>
              </v-window-item>
            </v-window>
          </v-card>
        </v-col>

        <!-- <v-col cols="12" md="6" class="mx-auto">
              <v-card class="mx-auto">

                <v-card-title>
                  <v-img src="/imgs/logo.png" height="200"></v-img>
                  <h3 class="font-weight-black text-center">AeroCast</h3>
                </v-card-title>

                <v-card-text class="bg-surface-light pt-4">
                  <v-form fast-fail @submit.prevent>
                    <v-text-field
                    label="Email: "
                    variant="outlined">
                  </v-text-field>

                  <v-text-field
                    label="Password: "
                    type="password"
                    variant="outlined">
                  </v-text-field>

                  <v-btn class="mt-2" 
                    type="submit" 
                    block>Submit</v-btn>
                  </v-form>

                  <v-divider class="my-5"></v-divider>
                  <h5 class="text-center">Don't have an account? <RouterLink to="/register" class="text-primary">Click here to Register</RouterLink></h5>
                </v-card-text>
              </v-card>
            </v-col> -->
      </v-row>
    </template>
  </AppLayout>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      step: -1, // Start with the "Sign In" window
    };
  },
  methods: {
    nextStep() {
      if (this.step < 2) {
        this.step++;
      }
    },
    previousStep() {
      if (this.step > -1) {
        this.step--;
      }
    },
  },
};


</script>

<style scoped>
.custom-border {
  border: 1px solid #fff;
  /* Change the color as needed */
}
</style>

<style>
body {
  font-family: 'Source Sans Pro', sans-serif;
}
</style>