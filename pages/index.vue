<template>
  <v-app>
    <v-container fluid>
      <v-row no-gutters>
        <v-col cols="12" lg="6" class="d-flex align-center justify-center">
          <v-row>
            <v-col cols="12" class="d-flex align-center justify-center flex-column">
              <div class="pt-0">
                <v-container>
                    <v-row class="flex-column">
                        <v-col>
                            <p class="display-1 text-center font-weight-medium my-5">
                                Create your account
                            </p>
                            <p class="text-center text--disabled">
                                Let's get started with your 30 days free trial
                            </p>
                            <v-btn 
                                height="45"
                                block
                                rounded
                                text
                                outlined
                                class="text-capitalize"
                            >
                                <v-img src="/google.svg" max-width="30" class="mr-4"></v-img>
                                Login with Google
                            </v-btn>
                        </v-col>

                        <v-col cols="12" class="d-flex align-center">
                            <v-divider></v-divider>

                            <span class="px-5"> or </span>
                            
                            <v-divider></v-divider>
                        </v-col>

                        <v-form>
                            <v-col class="py-0" v-for="(item, index) in form" :key="index">
                                <p class="my-1">
                                    {{ item.label }} <span class="red--text"><strong>* </strong></span>
                                </p>
                                <v-text-field
                                    :v-model="item.value"
                                    :placeholder="item.placeholder"
                                    :type="item.type"
                                    outlined
                                    rounded
                                    required
                                ></v-text-field>
                            </v-col>

                            <v-col class="py-0">
                                <v-checkbox label="I agree to all Term, Privacy Policy and Fees"></v-checkbox>
                                <v-btn
                                    class="text-capitalize white--text"
                                    color="black"
                                    @click="login"
                                    block
                                    rounded
                                >
                                    Sign Up
                                </v-btn>
                                <p class="mt-2">
                                    Already have an account?
                                    <a class="primary--text">Log in</a>
                                </p>
                            </v-col>
                        </v-form>
                    </v-row>
                </v-container>
              </div>
            </v-col>
          </v-row>
        </v-col>

        <v-col cols="6" class="d-none d-md-none d-lg-flex">
          <v-container class="d-flex">
            <v-card rounded="xl">
                <v-img src="/furniture-2.avif" height="100%" class="d-flex align-end justify-center">
                    <div class="white--text text-center mx-10 mb-10">
                        <p class="text-h4">
                            Discovering the Best
                            Furniture for Your Home
                        </p>
                        <p>
                            Our practice is Designing Complete Environments exceptional buildings communities and place in special situations
                        </p>
                        
                        <v-row>
                            <v-col v-for="(item, index) in transparentBtn" :key="index" :cols="item.col">
                                <v-btn color="white" outlined rounded>
                                    <v-card-text class="white--text">
                                        <v-icon :class="item.icon"></v-icon> 
                                        {{ item.text }}
                                    </v-card-text>
                                </v-btn>
                            </v-col>
                        </v-row>
                    </div>
                </v-img>
            </v-card>
          </v-container>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
  export default {
    name: 'Login',
    data() {
      return {
        form: {
            name: {
                label: "Name",
                placeholder: "Enter your name",
                value: "",
                typle: "text"
            },
            email: {
                label: "Email",
                placeholder: "Enter your email",
                value: "",
                typle: "email"
            },
            password: {
                label: "Password",
                placeholder: "Enter your password",
                value: "",
                typle: "password"
            },
        },
        transparentBtn: {
            guarantee: {
                col: "5",
                icon: "mdi mdi-check-decagram-outline",
                text: "100% Guarantee"
            },
            delivery: {
                col: "7",
                icon: "mdi mdi-truck-check-outline",
                text: "Free delivery London area"
            },
        }
      }
    },
    methods: {
      login(){
        console.log('log in');
      }
    },
  }
</script>
