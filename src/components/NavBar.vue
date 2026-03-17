<script setup>
import {useRouter} from "vue-router";
import {useAuth} from '../services/auth'

 const { logout } = useAuth()
 const router = useRouter();

const isLoggedIn = localStorage.getItem("authToken")
const isAdmin = true
</script>
<template>
    <v-app-bar color="primary">
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
                        <v-btn color="primary" to="/profile">Profile</v-btn>                        
                    </v-list-item>
                    <v-list-item>
                        <v-btn color="primary" @click="()=>{logout (); router.push('/')}">Logout</v-btn>                        
                    </v-list-item>
                </v-list>
            </v-menu>
        </v-btn>
        <v-btn to="/login" v-else>Login</v-btn>
    </v-app-bar>
</template>