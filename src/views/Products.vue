<template>
    <div id="app">
        <v-app id="inspire">
            <!-- texto titulo  -->
            <v-container fluid fill-height class="green lighten-4">
                <v-layout justify-center align-center column pa-5>
                    <div
                        class="display-3 font-weight-black black--text text-xs-center pt-5"
                    >
                        OUR SERVICES
                    </div>
                </v-layout>
            </v-container>
            <!-- products  -->
            <v-container grid-list-lg class="como-funciona">
                <v-layout row wrap>
                    <!-- 1 product  -->
                    <v-flex xs12 sm12 md4>
                        <v-card class="mx-auto" max-width="344">
                            <v-img
                                src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                                height="200px"
                            ></v-img>

                            <v-card-title>
                                Name
                            </v-card-title>

                            <v-card-subtitle>
                                PRICE $$$
                            </v-card-subtitle>

                            <v-card-actions>
                                <v-spacer></v-spacer>

                                <v-btn icon @click="show = !show">
                                    <v-icon>{{
                                        show
                                            ? 'mdi-chevron-up'
                                            : 'mdi-chevron-down'
                                    }}</v-icon>
                                </v-btn>
                            </v-card-actions>

                            <v-expand-transition>
                                <div v-show="show">
                                    <v-divider></v-divider>

                                    <v-card-text>
                                        DESCRIPTION OF THE SERVICE--he promised
                                        more than he could deliver. You won't
                                        have time for sleeping, soldier, not
                                        with all the bed making you'll be doing.
                                        Then we'll go with that data file! Hey,
                                        you add a one and two zeros to that or
                                        we walk! You're going to do his laundry?
                                        I've got to find a way to escape.
                                    </v-card-text>
                                </div>
                            </v-expand-transition>
                        </v-card>
                    </v-flex>

                    <!-- 2 product  -->

                    <v-flex xs12 sm12 md4>
                        <v-card class="mx-auto" max-width="344">
                            <v-img
                                src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                                height="200px"
                            ></v-img>

                            <v-card-title>
                                Name
                            </v-card-title>

                            <v-card-subtitle>
                                PRICE $$$
                            </v-card-subtitle>

                            <v-card-actions>
                                <v-spacer></v-spacer>

                                <v-btn icon @click="show = !show">
                                    <v-icon>{{
                                        show
                                            ? 'mdi-chevron-up'
                                            : 'mdi-chevron-down'
                                    }}</v-icon>
                                </v-btn>
                            </v-card-actions>

                            <v-expand-transition>
                                <div v-show="show">
                                    <v-divider></v-divider>

                                    <v-card-text>
                                        DESCRIPTION OF THE SERVICE--he promised
                                        more than he could deliver. You won't
                                        have time for sleeping, soldier, not
                                        with all the bed making you'll be doing.
                                        Then we'll go with that data file! Hey,
                                        you add a one and two zeros to that or
                                        we walk! You're going to do his laundry?
                                        I've got to find a way to escape.
                                    </v-card-text>
                                </div>
                            </v-expand-transition>
                        </v-card>
                    </v-flex>

                    <!-- 3 product  -->

                    <v-flex xs12 sm12 md4>
                        <v-card class="mx-auto" max-width="344">
                            <v-img
                                src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                                height="200px"
                            ></v-img>

                            <v-card-title>
                                Name
                            </v-card-title>

                            <v-card-subtitle>
                                PRICE $$$
                            </v-card-subtitle>

                            <v-card-actions>
                                <v-spacer></v-spacer>

                                <v-btn icon @click="show = !show">
                                    <v-icon>{{
                                        show
                                            ? 'mdi-chevron-up'
                                            : 'mdi-chevron-down'
                                    }}</v-icon>
                                </v-btn>
                            </v-card-actions>

                            <v-expand-transition>
                                <div v-show="show">
                                    <v-divider></v-divider>

                                    <v-card-text>
                                        DESCRIPTION OF THE SERVICE--he promised
                                        more than he could deliver. You won't
                                        have time for sleeping, soldier, not
                                        with all the bed making you'll be doing.
                                        Then we'll go with that data file! Hey,
                                        you add a one and two zeros to that or
                                        we walk! You're going to do his laundry?
                                        I've got to find a way to escape.
                                    </v-card-text>
                                </div>
                            </v-expand-transition>
                        </v-card>
                    </v-flex>
                </v-layout>
            </v-container>
        </v-app>
    </div>
</template>

<script>
export default {
    name: 'Products',
    data() {
        return {
            show: false
        };
    }
};
</script>

<style scoped></style>
