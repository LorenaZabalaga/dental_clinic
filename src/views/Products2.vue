<template>
    <div id="app">
        <v-app id="inspire">
            <!-- texto titulo  -->
            <v-container fluid fill-height class="teal lighten-4">
                <v-layout justify-center align-center column pa-5>
                    <div
                        class="display-3 font-weight-black teal--text dark text-xs-center pt-5"
                    >
                        OUR SERVICES
                    </div>
                </v-layout>
            </v-container>
            <!-- products  -->
            <v-container grid-list-lg class="como-funciona">
                <v-layout row wrap>
                    <!-- 1 product  -->
                    <v-flex
                        xs12
                        sm12
                        md4
                        v-for="card in info"
                        :key="card.content"
                    >
                        <v-card class="mx-auto" max-width="344">
                            <v-img height="200px" :src="card.src"></v-img>

                            <v-card-title primary-title>
                                <div>
                                    <div class="headline">{{ card.title }}</div>
                                    <span class="grey--text">{{
                                        card.subtitle
                                    }}</span>
                                <v-divider></v-divider>
                                <v-spacer></v-spacer> 
                                <v-spacer></v-spacer>                               
                                    <td class="body-1 text-xs-left mb-3 pt-5">{{ card.description  }}</td>                                    

                                </div>
                            </v-card-title>

                            <v-card-actions>
                                <v-spacer></v-spacer>




                            </v-card-actions>


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
            show: null,

            info: [
                {
                    title: 'NAME 1 ',
                    subtitle: ' PRICE $$$ 1',
                    description:
                        " 1 DESCRIPTION OF THE SERVICE--he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.",
                    src: 'http://source.unsplash.com/U1gvhqVQ2kQ',
                    exp: true
                },

                {
                    title: 'NAME 2 ',
                    subtitle: ' PRICE $$$ 2',
                    description:
                        " 2 DESCRIPTION OF THE SERVICE--he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.",
                    src: 'http://source.unsplash.com/WFsNCIn8OF4',
                    exp: false
                },
                {
                    title: 'NAME 3 ',
                    subtitle: ' PRICE $$$ 3',
                    description:
                        "3 DESCRIPTION OF THE SERVICE--he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.",
                    src: 'http://source.unsplash.com/cscGEQgrhMY',
                    exp: false
                }
            ]
        };
    }
};
</script>

<style scoped></style>
