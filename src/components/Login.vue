<script setup>
    import { ref } from 'vue'
    import {useRouter} from "vue-router"

    const router = useRouter();

    const rules = {
        required: value => !!value || 'Required.',
        min: v => v.length >= 8 || 'Min 8 characters',
        emailMatch: () => (`The email and password you entered don't match`),
    }

    const show1 = ref(false)
    const show2 = ref(true)
    const password = ref(null)
    const Username = ref(null)

    function login(){
        const userDetails = JSON.parse(localStorage.getItem('userDetails'))
        if (Username.value == userDetails.email && password.value == userDetails.password){
            //proceed to Homepage
            router.push('/homepage')
            localStorage.setItem("isLoggedIn", true);
        }else{
            console.log('Invalid credentials. Try again')
        }
    }
</script>
<template>
    <v-container  width="50%"; class="text-center mt-16">
        <v-row>
            <v-col md="12">
                <v-form>
                <v-row>
                        <v-col md="12">
                            <v-img src="macfit-logo3.png" width="100" class="mx-auto"></v-img>
                        </v-col>
                </v-row>
                    <v-row>
                        <v-col>
                            <div class="text-display-small font-weight-medium" style="font-family: Verdana, sans-serif; ">Welcome to MacFit Gym</div>
                        </v-col>
                    </v-row>
                        <v-row>
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right" style="font-family: Verdana, sans-serif;">Username</div>
                            </v-col>
                            <v-col md="6">
                                <v-text-field variant="outlined" v-model="Username"></v-text-field>
                            </v-col>
                        </v-row>
                         <v-row>
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right" style="font-family: Verdana, sans-serif;">Password</div>
                            </v-col>
                            <v-col md="6">
                                <v-text-field v-model="password"
                                    :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                                    :rules="[rules.required, rules.min]"
                                    :type="show1 ? 'text' : 'password'"
                                    hint="At least 8 characters"
                                    variant="outlined">
                                </v-text-field>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col md="12">
                              <v-btn color="#084A4A"variant="elevated" width="250" @click="login">Login</v-btn>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col md="12">
                                <div style="color: #084A4A; font-family: Verdana, sans-serif;">New to MacFit Gym? 
                                    <router-link to="/signup"> Create an account</router-link>
                                </div>
                            </v-col>
                        </v-row>
                </v-form>
            </v-col>
        </v-row>
    </v-container>
</template>   