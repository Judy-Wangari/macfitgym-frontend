<script setup>
import {ref} from 'vue'

const userDetails = JSON.parse(localStorage.getItem('user'))
const selectedItem = ref(['overview'])

</script>
<template>
  
            <v-navigation-drawer>
                    <template v-slot:prepend>
                        <v-list-item
                            lines="two"
                            prepend-icon="mdi-account-circle"
                            subtitle="Logged in"
                            
                        ></v-list-item>
                    </template>

                    <v-divider></v-divider>

                    <v-list density="compact" nav v-model:selected="selectedItem" mandatory>
                    <v-list-item prepend-icon="mdi-view-dashboard" title="Overview" value="overview" class="pa-8"></v-list-item>
                    <v-list-item prepend-icon="mdi-weight-lifter" title="Workout" value="workout"  class="pa-8"></v-list-item>
                    <v-list-item prepend-icon="mdi-food-apple" title="Diet Plan" value="dietplan"  class="pa-8"></v-list-item>
                    </v-list>
            </v-navigation-drawer>

            <!--Homepage content-->
           <v-container>
            <!--overview-->
        <div v-if="selectedItem[0] === 'overview'">
                    <v-img  src="overview.jpg" height="200" cover class="mb-6">
                    <div style="height: 100; display: flex; align-items: center; justify-content: center; " >
                        <div>
                        <h1 style="color: white; font-size: 36px;"> Welcome Back ! </h1>
                        <p style="color: white; text-align: center;">We are glad you are here</p>
                        </div>
                    </div>
                    </v-img>
            

                <!--Cards-->
                <v-row size="3" >
                    <v-col >
                        <v-card class="mt-6" style="text-align: center;">
                        <v-icon color="#0097A7" icon="mdi-fire" size="large" class="mt-2"></v-icon>
                            <v-card-title>Calories Burned</v-card-title>
                            <v-card-text class=" font-weight-light" >2,234 kcal</v-card-text>
                        </v-card>
                    </v-col>
                <v-col >
                        <v-card class="mt-6" style="text-align: center;">
                            <v-icon color="#0097A7" icon="mdi-bullseye-arrow" size="large" class="mt-2"></v-icon>
                            <v-card-title>Goals achieved</v-card-title>
                            <v-card-text class=" font-weight-light">3</v-card-text>
                        </v-card>
                    </v-col>
                <v-col >
                        <v-card class="mt-6" style="text-align: center;">
                            <v-icon color="#0097A7" icon="mdi-calendar-check" size="large" class="mt-2"></v-icon>
                            <v-card-title>Days Active</v-card-title>
                            <v-card-text class=" font-weight-light">20</v-card-text>
                        </v-card>
                    </v-col>
                </v-row>
                <v-row size="1">
                    <v-col>
                        <v-card class="mt-6 pa-8"  style="text-align: center;">
                            <v-card-title style="color: #0097A7; font-size: 25px;">Current Subscription </v-card-title>
                            <v-card-text class=" font-weight-light" style=" font-size: 20px;">You have no active plan. Choose a plan to get started!</v-card-text>
                            <v-btn style="color: #0097A7;" to="/bundles">Choose plan</v-btn>
                        </v-card>
                    </v-col>
                </v-row>
            </div>
            <!--workout-->
            <div v-if="selectedItem[0] === 'workout'">
               
                 <v-row>
                        <div>
                            <h1 style="color: #0097A7;">Leg Workout</h1>
                        </div>
                    </v-row>
                 <v-row>
                       <v-col md="4">
                            <v-card>
                                    <v-img src="tred1.jpg" cover></v-img>
                                    <v-card-title>Treadmill Running</v-card-title>
                                    <v-card-text>Build stamina and burn calories with our state-of-the-art treadmills.
                                    </v-card-text>
                                    <v-btn color="#0097A7">READ MORE</v-btn>
                            </v-card>
                        </v-col>
                        <v-col md="4">
                            <v-card >
                                <v-img src="pol1.jpg" cover></v-img>
                                <v-card-title>Plyometric Training</v-card-title>
                                <v-card-text> Explosive power and agility training to take your fitness to the next level.</v-card-text>
                                <v-btn color="#0097A7">READ MORE</v-btn>
                            </v-card>
                        </v-col>
                        <v-col md="4">
                          <v-card>
                                <v-img src="workout3.jpg" cover></v-img>
                                    <v-card-title>Leg Press</v-card-title>
                                    <v-card-text>Build strong, powerful legs with our professional weight machines.</v-card-text>
                                    <v-btn color="#0097A7">READ MORE</v-btn>
                          </v-card>
                        </v-col>
                </v-row>
<!--HANDWORKOUT-->
                    <v-row>
                        <div>
                            <h1 style="color: #0097A7;">Arms & Hands </h1>
                        </div>
                    </v-row>
                 <v-row>
                       <v-col md="4">
                            <v-card>
                                    <v-img src="med1.jpg" cover></v-img>
                                    <v-card-title>Medicine Ball Push-ups</v-card-title>
                                    <v-card-text>Challenge your chest, arms and core with medicine ball push-ups. Perfect for building upper body stability and strength.
                                    </v-card-text>
                                    <v-btn color="#0097A7">READ MORE</v-btn>
                            </v-card>
                        </v-col>
                        <v-col md="4">
                            <v-card >
                                <v-img src="bi1.jpg" cover></v-img>
                                <v-card-title>Bicep Curls</v-card-title>
                                <v-card-text> Sculpt and define your biceps with dumbbell curls. Start light, stay consistent and watch your arms transform.</v-card-text>
                                <v-btn color="#0097A7">READ MORE</v-btn>
                            </v-card>
                        </v-col>
                        <v-col md="4">
                          <v-card>
                                <v-img src="ba1.jpg" cover></v-img>
                                    <v-card-title>Battle Ropes</v-card-title>
                                    <v-card-text>A full arm and shoulder burner. Battle ropes build explosive power, endurance and grip strength all at once.</v-card-text>
                                    <v-btn color="#0097A7">READ MORE</v-btn>
                          </v-card>
                        </v-col>
                </v-row>
</div>
            <!--Diet Plan-->
            <div v-if="selectedItem[0] === 'dietplan'">
               <v-row size="4">
                <v-col>
                    <v-card class="text-center" style="height: 100%;">
                        <v-icon color="#0097A7" icon="mdi-weather-sunset-up" size="large" class="mt-2"></v-icon>
                        <v-card-title  style=" color:#0097A7">Breakfast</v-card-title>
                        <v-card-text>
                            <v-list style="font-size: 20px;">
                                <v-list-item>1 Scrummbled egg</v-list-item>
                                <v-list-item>1 Slice whole wheat toast</v-list-item>
                                <v-list-item>1/2 cup Strawberries</v-list-item>
                           </v-list>
                        </v-card-text>
                    </v-card>
                </v-col>
                <v-col>
                    <v-card class="text-center" style="height: 100%;">
                        <v-icon color="#0097A7" icon="mdi-weather-sunny" size="large" class="mt-2"></v-icon>
                        <v-card-title  style="color:#0097A7">Lunch</v-card-title>
                        <v-card-text >
                            <v-list style="font-size: 20px;">
                                <v-list-item>Grilled chicken breast</v-list-item>
                                <v-list-item>1 cup mixed greens</v-list-item>
                                <v-list-item>1/2 cup cucumber</v-list-item>
                                <v-list-item>1/2 tps olive oil</v-list-item>
                           </v-list>
                        </v-card-text>
                    </v-card>
                </v-col>
                <v-col>
                    <v-card class="text-center" style="height: 100%;">
                        <v-icon color="#0097A7" icon="mdi-weather-night" size="large" class="mt-2 "></v-icon>
                        <v-card-title  style=" color:#0097A7">Dinner</v-card-title>
                        <v-card-text >
                            <v-list style="font-size: 20px;">
                                <v-list-item>Baked Salmon</v-list-item>
                                <v-list-item>1/2 cup steamed broccoli</v-list-item>
                                <v-list-item>1/2 cup quinoa</v-list-item>
                           </v-list>
                        </v-card-text>
                    </v-card>
                </v-col>
                 <v-col>
                 <v-card class="text-center " style="height: 100%;" >
                        <v-icon color="#0097A7" icon="mdi-food-apple" size="large" class="mt-2"></v-icon>
                        <v-card-title  style=" color:#0097A7">Snack</v-card-title>
                        <v-card-text >
                            <v-list style="font-size: 20px;">
                                <v-list-item>1 small Apple</v-list-item>
                           </v-list>
                        </v-card-text>
                    </v-card>
                     </v-col>
               </v-row>
               <v-row>
        <v-col md="12">
             <v-card class="text-center pa-6" >
                <v-icon color="#0097A7" icon="mdi-food" size="large" class="mt-8"></v-icon>
                <v-card-title style=" color:#0097A7">Daily Nutrition Summary</v-card-title>
                <v-card-text style=" color:#0097A7; font-size: 20px;">A balanced diet plan designed to fuel your workouts and support your fitness goals.</v-card-text>
            </v-card>
        </v-col>
     </v-row>
            </div>
           </v-container>
</template>   