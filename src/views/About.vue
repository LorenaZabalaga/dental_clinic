<template>
    <!-- imagenes  -->

    <v-container fluid class="teal lighten-4">
        <v-layout fill-height column pa-5>
            <v-carousel
                cycle
                height="350"
                hide-delimiter-background
                show-arrows-on-hover
            >
                <v-carousel-item
                    v-for="(item, i) in items"
                    :key="i"
                    :src="item.src"
                ></v-carousel-item>
            </v-carousel>
        </v-layout>

        <v-container grid-list-lg>
            <v-layout column>
                <v-flex
                    class="display-2 font-weight-bold teal--text text-xs-center my-5"
                    >How It Works</v-flex
                >
                <v-flex>
                    <div class="headline mt-3 teal--text font weight-bold">
                        Lorem ipsum
                    </div>
                    <p class="subheading mt-3">
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Totam animi eveniet vitae vel illum placeat
                        repudiandae inventore.
                    </p>
                </v-flex>
                <v-flex>
                    <div class="headline mt-3 teal--text font weight-bold">
                        Lorem ipsum
                    </div>
                    <p class="subheading mt-3">
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Totam animi eveniet vitae vel illum placeat
                        repudiandae inventore.
                    </p>

                    <p class="subheading mt-3">
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Totam animi eveniet vitae vel illum placeat
                        repudiandae inventore.
                    </p>

                    <p class="subheading mt-3">
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Totam animi eveniet vitae vel illum placeat
                        repudiandae inventore.
                    </p>
                </v-flex>
                <v-flex>
                    <div class="headline mt-3 teal--text font-weight-bold">
                        Lorem ipsum
                    </div>
                    <p class="subheading mt-3">
                        Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Totam animi eveniet vitae vel illum placeat
                        repudiandae inventore.
                    </p>
                </v-flex>
            </v-layout>
        </v-container>
    </v-container>
</template>

<script>
export default {
    name: 'About',

    data() {
        return {
            items: [
                {
                    src: 'http://source.unsplash.com/D0ov97Td-xM'
                },
                {
                    src: 'http://source.unsplash.com/mpr5QrN9rjM'
                }
            ]
        };
    }
};
</script>

<style scoped></style>
