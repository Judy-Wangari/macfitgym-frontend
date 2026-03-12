<script setup>

</script>

<template>
<v-container max-width="100%">
    <v-row>
        <v-carousel>
            <v-carousel-item src="/landscape1.jpg" cover></v-carousel-item>
            <v-carousel-item src="/landscape2.jpg" cover></v-carousel-item>
            <v-carousel-item src="/landscape3.jpg" cover></v-carousel-item>
        </v-carousel>
    </v-row>
</v-container>

<!-- About Us -->
     <v-container  max-width="100%">
        <v-row >
            <v-col md="8" class="text-center">
                <div class="text-display-medium mb-12">Built for Those Who Push Limits</div>
                <div class="text-title-large font-weight-light text-medium-emphasis mb-8">We're more than just a gym — we're a movement. A community of dedicated athletes, passionate beginners, and everyone in between, all united by one common goal: to become the best version of themselves. From the moment you walk through our doors, you'll feel the energy, the drive, and the commitment that sets us apart from the rest.</div>
                <div class="text-title-large font-weight-light text-medium-emphasis mb-8">Our world-class facilities are open 24 hours a day, 7 days a week, because we know your schedule doesn't always follow the rules. Featuring the latest commercial-grade equipment, expansive free weight areas, dedicated cardio zones, and specialized studios for HIIT, yoga, and functional training — everything you need to crush your workout is right here under one roof.</div>
                <div class="text-title-large font-weight-light text-medium-emphasis mb-8">No matter where you are on your fitness journey, our team of certified personal trainers and nutrition coaches are here to support you every step of the way. We build personalized programs tailored to your body, your goals, and your lifestyle — because cookie-cutter plans don't build extraordinary results. Your transformation starts here, and we'll be with you every rep, every set, every milestone.</div>
                <v-btn color="#0097A7">LEARN MORE</v-btn>
            </v-col>
            <v-col md="4 ">
                <v-container class ="d-flex align-center justify-center fill-height">
                <v-img src="aboutus.jpg"></v-img>
                </v-container>
            </v-col>
        </v-row>
     </v-container>

     <v-container>
        <v-row>
            <v-col md="4">
                <v-card>
                    <v-img src="news1.jpg" cover></v-img>
                    <v-card-title>Stay Hydrated, Stay Active</v-card-title>
                    <v-card-text>Fuel your fitness journey with the Quokka water bottle — designed for 
                                on-the-go hydration. Whether you're at yoga, jumping rope, or hitting 
                                the gym, keep your water fresh with ice and lemon all session long.
                    </v-card-text>
                    <v-btn color="#0097A7">READ MORE</v-btn>
                </v-card>
            </v-col>
            <v-col md="4">
                <v-card>
                    <v-img src="news2.jpg" cover></v-img>
                    <v-card-title>Run Your Own Race</v-card-title>
                    <v-card-text> Every great journey starts with a single step. Hit the open road, breathe 
            in the fresh air, and push your limits — one mile at a time. Discover the 
            freedom that comes with outdoor running and build a healthier you.</v-card-text>
                    <v-btn color="#0097A7">READ MORE</v-btn>
                </v-card>
            </v-col>
            <v-col md="4">
                <v-card>
                    <v-img src="news3.jpg" cover></v-img>
                    <v-card-title>Find Your Balance Together</v-card-title>
                    <v-card-text>There's power in practicing together. Join a community of like-minded 
                souls and take your yoga practice to new heights — even beachside. 
                Ground yourself, breathe deep, and rise as one.</v-card-text>
                    <v-btn color="#0097A7">READ MORE</v-btn>
                </v-card>
            </v-col>
        </v-row>
    </v-container>

    <!--Reviews-->
    <v-container>
        <v-row>
            <v-col md="3">
                <v-card >
                    <v-card-text>"Best fitness community I've ever joined. I feel stronger and more energized than ever!"</v-card-text>
                    <v-rating :length="5" :size="32" :model-value="3" active-color="#0097A7"></v-rating>
                </v-card>
            </v-col>
            <v-col md="3">
                <v-card >
                    <v-card-text> "Great trainers, great community. My running performance has never been better!"</v-card-text>
                    <v-rating :length="5" :size="32" :model-value="2" active-color="#0097A7"></v-rating>
                </v-card>
            </v-col>
            <v-col md="3">
                <v-card >
                    <v-card-text>"The beach yoga sessions completely changed my mindset. Absolutely worth it!"</v-card-text>
                    <v-rating :length="5" :size="32" :model-value="4" active-color="#0097A7"></v-rating>
                </v-card>
            </v-col>
            <v-col md="3">
                <v-card >
                    <v-card-text> "From day one I felt welcomed. The workouts are challenging but so rewarding!"</v-card-text>
                    <v-rating :length="5" :size="32" :model-value="5" active-color="#0097A7"></v-rating>
                </v-card>
            </v-col>
        </v-row>
    </v-container>

    <!--Contact Us-->
    <v-container max-width="100%" style="background-color: teal; border: 1px solid black ;" >
        <v-row class="text-center" style="color: white;" >
            <div  class="text-title-large font-weight-bold  mb-2 ">Get in Touch</div>
            <div  class="text-title-large font-weight-bold  mb-2">0712 345 678 | macfitgym@gmail.com</div>
            <div  class="text-title-large font-weight-bold  mb-2">Opening Hours</div>
            <div  class="text-title-large font-weight-bold  mb-2">Mon-Fri: 5.00am - 9.00pm | Sat: 5.30am - 6pm | Sun: 8.00am - 2.00pm</div>
            <div  class="text-title-large font-weight-bold  mb-2">MacFit Gym, 3rd Floor Nairobi Mall, Nairobi Road</div>
            <div  class="text-title-large font-weight-bold  mb-2">&copy; 2026 MacFit Gym. Design by Daniellah Designs</div>
        </v-row>
    </v-container>
    
</template>     