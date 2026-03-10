<script setup>
    import { ref } from 'vue'

    const rules = {
        required: value => !!value || 'Required.',
        min: v => v.length >= 8 || 'Min 8 characters',
        emailMatch: () => (`The email and password you entered don't match`),
    }

    const show1 = ref(false)
    const show2 = ref(true)
    const password = ref(null)

    const confirmPassword= ref(null)
    const show1confirm = ref(false)
</script>
<template>
    <v-container width="50%" class="text-center mt-16" >
        <v-row>
            <v-col md="12">
                <v-form>
                <v-row>
                        <v-col md="12">
                            <v-icon>mdi-weight-lifter</v-icon>
                        </v-col>
                </v-row>
                    <v-row>
                        <v-col>
                            <div class="text-display-small font-weight-medium">Sign up to MacFit Gym</div>
                        </v-col>
                    </v-row>
                        <v-row>
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right">Firstname</div>
                            </v-col>
                            <v-col md="6">
                                <v-text-field variant="outlined"></v-text-field>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right">Lastname</div>
                            </v-col>
                            <v-col md="6">
                                <v-text-field variant="outlined"></v-text-field>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right">Email</div>
                            </v-col>
                            <v-col md="6">
                                <v-text-field variant="outlined"></v-text-field>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right">Phone Number</div>
                            </v-col>
                            <v-col md="6">
                                <v-text-field variant="outlined" type="number"></v-text-field>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right">Gender</div>
                            </v-col>
                            <v-col md="6">
                               <v-radio-group inline>
                                    <v-radio label="Female" value="female"></v-radio>
                                    <v-radio label="Male" value="male"></v-radio>
                              </v-radio-group>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right">Date of Birth</div>
                            </v-col>
                            <v-col md="6">
                                <v-date-input variant="outlined"></v-date-input>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right">Gym location</div>
                            </v-col>
                            <v-col md="6">
                                <v-select
                                    label="Select"
                                    :items="['CBD', 'Madaraka', 'Westlands', 'Buruburu']"
                                    variant="outlined"
                               ></v-select>
                            </v-col>
                        </v-row>
                         <v-row>
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right">Password</div>
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
                            <v-col md="6">
                                <div class="text-title-large font-weight-medium text-right">Confirm password</div>
                            </v-col>
                            <v-col md="6">
                                <v-text-field 
                                    v-model="confirmPassword"
                                    :append-icon="show1confirm ? 'mdi-eye' : 'mdi-eye-off'"
                                    :rules="[rules.required, rules.min]"
                                    :type="show1confirm ? 'text' : 'password'"
                                    hint="At least 8 characters"
                                    variant="outlined">
                                </v-text-field>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col md="12">
                              <v-btn color="#084A4A"variant="elevated" >Sign up</v-btn>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col md="12">
                                <div>New to MacFit Gym? Create an account</div>
                            </v-col>
                        </v-row>
                </v-form>
            </v-col>
        </v-row>
    </v-container>
</template>   