<script setup>
import{ref} from 'vue'
import{useRouter} from "vue-router"

const router = useRouter();

const showBundleDialog = ref(false)
const isLoggedIn = localStorage.getItem( "isLoggedIn")
const selectedBundle = ref(null)
const selectedPrice = ref(null)

function showBundle(name, price){
    if(isLoggedIn){
        selectedBundle.value = name
        selectedPrice.value = price
        showBundleDialog.value = true //open popup
    }else{
        router.push('/login')
    }
}
function subscribe(){
     const userDetails = JSON.parse(localStorage.getItem('userDetails'))
     userDetails.subscription = {
        name: selectedBundle.value,
        price: selectedPrice.value
     }
     localStorage.setItem('userDetails',JSON.stringify(userDetails))
     showBundleDialog.value = false
}
</script>
<template>
<v-container  class="mt-16">
    <v-row>
        <v-col>
        <div class="text-display-medium mb-12 ">Bundles and Pricing</div>
        </v-col>
    </v-row>
    <v-row>
        <v-col>
            <div class ="text-lable-medium font-italic">Click on a bundle to subscribe</div>
        </v-col>
    </v-row>
    <v-row>
        <v-col md="3">
            <v-card class="text-center pa-6 " @click="showBundle('Daily Pass', 500)">
                <v-icon color="#0097A7" icon="mdi-clock-outline" size="large" class="mt-8" ></v-icon>
                <v-card-title color="#0097A7">Daily Pass</v-card-title>
                <v-card-text>500 Ksh</v-card-text>
            </v-card>
        </v-col>
        <v-col md="3">
            <v-card class="text-center pa-6" @click="showBundle('1 month', 2500)">
                <v-icon color="#0097A7" icon="mdi-calendar-blank" size="large" class="mt-8"></v-icon>
                <v-card-title color="#0097A7">1 month</v-card-title>
                <v-card-text>2,500 Ksh</v-card-text>
            </v-card>
        </v-col>
        <v-col md="3">
            <v-card class="text-center pa-6" @click="showBundle('3 months',5000)">
                <v-icon color="#0097A7" icon="mdi-calendar" size="large" class="mt-8"></v-icon>
                <v-card-title color="#0097A7">3 months</v-card-title>
                <v-card-text>5,000 Ksh</v-card-text>
            </v-card>
        </v-col>
        <v-col md="3">
            <v-card class="text-center pa-6" @click="showBundle('6 months',25000)">
                <v-icon color="#0097A7" icon="mdi-calendar-blank-multiple" size="large" class="mt-8"></v-icon>
                <v-card-title color="#0097A7">6 months</v-card-title>
                <v-card-text>25,000 Ksh</v-card-text>
            </v-card>
        </v-col>
    </v-row>
    <v-row>
        <v-col md="12">
             <v-card class="text-center pa-6" @click="showBundle('Annual',40000)">
                <v-icon color="#0097A7" icon="mdi-crown" size="large" class="mt-8"></v-icon>
                <v-card-title color="#0097A7">Annual Premium</v-card-title>
                <v-card-text>40,000 Ksh — Best Value! Enjoy unlimited access, priority booking, and exclusive member perks all year long.</v-card-text>
            </v-card>
        </v-col>
     </v-row>
 </v-container>
 <!--What's Included-->
    <v-container>
        <v-row>
            <v-col md="12">
                <div class="text-display-small mb-12 mt-12 text-center" >What's included in yor bundle</div>
            </v-col>
        </v-row>
        <v-row>
            <v-col md="3">
             <v-card class="text-center pa-6">
                <v-icon color="#0097A7" icon="mdi-dumbbell" size="large" class="mt-8"></v-icon>
                <v-card-title color="#0097A7">Gym Access</v-card-title>
            </v-card>
        </v-col>
        <v-col md="3">
             <v-card class="text-center pa-6">
                <v-icon color="#0097A7" icon="mdi-yoga" size="large" class="mt-8"></v-icon>
                <v-card-title color="#0097A7">Yoga & Classes</v-card-title>
            </v-card>
        </v-col>
        <v-col md="3">
             <v-card class="text-center pa-6">
                <v-icon color="#0097A7" icon="mdi-account-supervisor" size="large" class="mt-8"></v-icon>
                <v-card-title color="#0097A7">Personal Trainer</v-card-title>
            </v-card>
        </v-col>
        <v-col md="3">
             <v-card class="text-center pa-6">
                <v-icon color="#0097A7" icon="mdi-food-apple" size="large" class="mt-8"></v-icon>
                <v-card-title color="#0097A7">Nutrition Plan</v-card-title>
            </v-card>
        </v-col>
        </v-row>
        <v-row>
            <v-col md="3">
             <v-card class="text-center pa-6">
                <v-icon color="#0097A7" icon="mdi-shower" size="large" class="mt-8"></v-icon>
                <v-card-title color="#0097A7">Locker & shower</v-card-title>
            </v-card>
        </v-col>
        <v-col md="3">
             <v-card class="text-center pa-6">
                <v-icon color="#0097A7" icon="mdi-wifi" size="large" class="mt-8"></v-icon>
                <v-card-title color="#0097A7">Free Wi-Fi</v-card-title>
            </v-card>
        </v-col>
        </v-row>
    </v-container>

      <v-container>
        <v-row>
            <v-col>
                <div class="text-display-small mb-12 mt-16 text-center" >How to Join MacFit Gym</div>
            </v-col>
        </v-row>
        <v-row >
            <v-col>
                <v-list style="font-size: 20px;">
                    <v-list-item>1.Visit our gym or website and choose a bundle that suits your goals.</v-list-item>
                    <v-list-item>2.Fill in your registration form with your personal details.</v-list-item>
                    <v-list-item>3.Make your payment via M-Pesa, card, or cash at the front desk.</v-list-item>
                    <v-list-item>4.Receive your membership card and start your fitness journey today!</v-list-item>
                </v-list>
            </v-col>
        </v-row>
      </v-container>

      <!--Dialog-->
        <v-dialog v-model="showBundleDialog" max-width="600" >

      <v-card prepend-icon="mdi-account" title="Subscribe to Bundle" >
        <v-card-text>
          You are about to subscribe to {{ selectedBundle }} at {{ selectedPrice }}. Click on the button below to complete payment
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
         <v-spacer></v-spacer>
          <v-btn text="Close" variant="plain" @click="showBundleDialog = false" ></v-btn>
          <v-btn color="primary" variant="tonal" @click="subscribe()" >Subscribe</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>

</template>   