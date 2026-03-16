<script setup>
import {useRouter} from "vue-router";

const router = useRouter();

const isLoggedIn = localStorage.getItem("authToken")
const isAdmin = true
function logout(){
    localStorage.removeItem( "isLoggedIn")
    router.push('/')
}
</script>
<template>
    <v-app-bar color="#0097A7">
        <v-app-bar-title>
            <router-link to="/">
              <v-img src="macfit-logo2.png" width="100" height="80" ></v-img> 
           </router-link>
        </v-app-bar-title>
        <v-btn to="/homepage" v-if="isLoggedIn">Home</v-btn>
        <v-btn to="/bundles">Bundles</v-btn>
        <v-btn to="/gym_locations"> Our Gyms </v-btn>
        <v-btn to="/admin" v-if = "isAdmin">Admin</v-btn>
        <v-btn v-if="isLoggedIn" color="white" variant="text">
    <v-icon color="white" size="32">mdi-account-circle</v-icon>
            <v-menu activator="parent" >
                <v-list >
                    <v-list-item>
                        <v-btn color="black" to="/profile">Profile</v-btn>                        
                    </v-list-item>
                    <v-list-item>
                        <v-btn color="black" @click="logout()">Logout</v-btn>                        
                    </v-list-item>
                </v-list>
            </v-menu>
        </v-btn>
        <v-btn to="/login" v-else>Login</v-btn>
    </v-app-bar>
</template>