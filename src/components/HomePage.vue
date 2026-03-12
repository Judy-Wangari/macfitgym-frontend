<script setup>
import {ref} from 'vue'

const userName = localStorage.getItem('userName')
const selectedItem = ref(['overview'])

</script>
<template>
  
            <v-navigation-drawer>
                    <template v-slot:prepend>
                        <v-list-item
                            lines="two"
                            prepend-icon="mdi-account-circle"
                            subtitle="Logged in"
                            :title="userName"
                        ></v-list-item>
                    </template>

                    <v-divider></v-divider>

                    <v-list density="compact" nav v-model:selected="selectedItem">
                    <v-list-item prepend-icon="mdi-view-dashboard" title="Overview" value="overview" class="pa-6"></v-list-item>
                    <v-list-item prepend-icon="mdi-weight-lifter" title="Workout" value="workout"  class="pa-6"></v-list-item>
                    <v-list-item prepend-icon="mdi-food-apple" title="Diet Plan" value="dietplan"  class="pa-6"></v-list-item>
                    <v-list-item prepend-icon="mdi-bullseye-arrow" title="Goal" value="goal"  class="pa-6"></v-list-item>
                    <v-list-item prepend-icon="mdi-chart-line" title="Progress" value="progress"  class="pa-6"></v-list-item>
                    </v-list>
            </v-navigation-drawer>

            <!--Homepage content-->
           <v-container>
            <!--overview-->
            <div v-if="selectedItem[0] === 'overview'">
                <h2>Welcome Back, {{ userName }}!</h2>
                <v-card>
                    <v-row size="4">
                        <v-col>
                            <v-card>
                                <v-card-title>Workout</v-card-title>
                            </v-card>
                        </v-col>
                        <v-col>
                            <v-card>
                                 <v-card-title>Diet Plan</v-card-title>
                            </v-card>
                        </v-col>
                        <v-col>
                            <v-card>
                                <v-card-title>Goal</v-card-title>
                            </v-card>
                        </v-col>
                        <v-col>
                            <v-card>
                                <v-card-title>Progress</v-card-title>
                            </v-card>
                        </v-col>
                    </v-row>
                </v-card>
            </div>
            <!--workout-->
            <div v-if="selectedItem[0] === 'workout'">
                <h2>Workout</h2>
                <v-card>
                    <v-row>
                        <v-col>
                            dftgrtg
                        </v-col>
                    </v-row>
                </v-card>
            </div>
            <!--Diet Plan-->
            <div v-if="selectedItem[0] === 'dietplan'">
               <h2>Diet Plan</h2>
            </div>
            <!--Goal-->
            <div v-if="selectedItem[0] === 'goal'">
               <h2>Goal</h2>
            </div>
            <!--Progress-->
            <div v-if="selectedItem[0] === 'progress'">
              <h2>Progress</h2>
            </div>

           </v-container>
</template>   