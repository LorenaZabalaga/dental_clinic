<template>
    <v-container fluid fill-height class="home-hi" style="max-height: 100vh;">
        <v-layout justify-center align-center column pa-5>
            <div class="display-4 font-weight-black white--text text-xs-center">
                GET YOU
            </div>
            <div
                class="display-4 font-weight-black white--text text-xs-center mb-3"
            >
                A NICE SMILE
            </div>
            <div class="display-1 font-weight-bold white--text text-xs-center">
                Without teeth, you can't eat. Get your appointment right now.
            </div>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    name: 'HomeHi'
};
</script>

<style scoped>
.home-hi {
    background: url('http://source.unsplash.com/By1szZOVpHg');
    background-size: cover;
    width: 100%;
    height: 100%;
}
</style>
