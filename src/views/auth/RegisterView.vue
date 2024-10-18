<script setup>
 import AppLayout from '@/components/layout/AppLayout.vue';
</script>

 <template>
    <AppLayout>
        <template #login_reg>
            <v-row>
            <v-col cols="12" md="6" class="mx-auto">
              <v-card class="mx-auto" prepend-icon="mdi-account-plus" subtitle="Register">
                <template v-slot:title>
                  <span class="font-weight-black">AeroCast</span>
                </template>

                <v-card-text class="bg-surface-light pt-4">
                  <v-form fast-fail @submit.prevent>

                  <v-text-field
                    label="First Name"
                    variant="outlined">
                  </v-text-field>

                  <v-text-field
                    label="Last Name"
                    variant="outlined">
                  </v-text-field>

                  <v-text-field
                    label="Email"
                    variant="outlined">
                  </v-text-field>

                  <v-text-field
                    label="Password"
                    type="password"
                    variant="outlined">
                  </v-text-field>

                  <v-text-field
                    label="Password Confirmation"
                    type="password"
                    variant="outlined">
                  </v-text-field>

                  <v-btn class="mt-2" 
                    type="submit" 
                    block>Submit</v-btn>
                  </v-form>

                  <v-divider class="my-5"></v-divider>
                  <h5 class="text-center">Already have an account? <RouterLink to="/login" class="text-primary">Click here LogIn</RouterLink></h5>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </template>
    </AppLayout>
 </template>