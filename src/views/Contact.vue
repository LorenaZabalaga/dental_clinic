<template>
    <div id="app">
        <v-app id="inspire">
            <!-- texto titulo  -->
            <v-container fluid class="teal lighten-4">
                <v-layout justify-center align-center column pa-5>
                    <div
                        class="display-3 font-weight-black teal--text text-xs-center pt-5"
                    >
                        LET'S CONNECT
                    </div>
                    <div
                        class="display-2 font-weight-black white--text text-xs-center pt-5"
                    >
                        We'd love to help you smile
                    </div>
                </v-layout>
            </v-container>

            <!-- products  -->
            <v-form ref="form">
                <v-container>
                    <v-row justify="left">
                        <v-col cols="12" sm="10" md="8" lg="6">
                            <v-card ref="form">
                                <v-card-text>
                                    <v-text-field
                                        v-model="from_fname"
                                        label="First Name"
                                        outlined
                                        :rules="from_fnameRules"
                                        required
                                    ></v-text-field>

                                    <v-text-field
                                        v-model="from_lname"
                                        label="Last Name"
                                        outlined
                                        :rules="from_lnameRules"
                                    ></v-text-field>

                                    <v-text-field
                                        v-model="from_email"
                                        label="Email"
                                        outlined
                                        left
                                        hint="Type your email address"
                                        :rules="from_emailRules"
                                        required
                                    ></v-text-field>

                                    <v-textarea
                                        label="Message"
                                        v-model="message"
                                        auto-grow
                                        outlined
                                        rows="4"
                                        row-height="30"
                                        :rules="messageRules"
                                        value=""
                                        hint="Leave us a comment"
                                        required
                                    ></v-textarea>
                                    <v-alert
                                        :value="alert"
                                        v-model="alert"
                                        type="success"
                                        dismissible
                                        transition="scale-transition"
                                    >
                                        Thank you! Your message has been sent
                                        successfully
                                    </v-alert>
                                </v-card-text>

                                <v-divider class="mt-12"></v-divider>
                                <v-card-actions>
                                    <v-btn @click="clear" text>Cancel</v-btn>
                                    <v-spacer></v-spacer>

                                    <v-btn
                                        :disabled="!valid"
                                        :loading="loading"
                                        color="primary"
                                        text
                                        @click="submit"
                                        @click.native="loader = 'loading'"
                                    >
                                        Submit
                                    </v-btn>
                                </v-card-actions>
                            </v-card>
                        </v-col>

                        <!-- LOCATION  -->
                        <v-col cols="12" sm="10" md="8" lg="6">
                            <iframe
                                src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2780.9385717559085!2d15.977909815084923!3d45.8124886181574!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x4765d6fe43f02b95%3A0xffb8d318ab73d33d!2sJuri%C5%A1i%C4%87eva%20ul.%209%2C%2010000%2C%20Zagreb%2C%20Croatia!5e0!3m2!1sen!2scl!4v1578622318766!5m2!1sen!2scl"
                                width="600"
                                height="450"
                                frameborder="0"
                                style="border:0;"
                                allowfullscreen=""
                            ></iframe>

                            <p>Address Zagreb, Croatia.</p>
                            <p>mail@dentalclinic.com</p>
                            <p>(351) 87654321</p>

                            <div class="text-right">
                                <v-btn
                                    class="mx-2"
                                    fab
                                    dark
                                    small
                                    color="primary"
                                    href="https://www.facebook.com/"
                                >
                                    <v-avatar>
                                        <img src="../../src/assets/fb.png" />
                                    </v-avatar>
                                </v-btn>
                                <v-btn
                                    class="mx-2"
                                    fab
                                    dark
                                    small
                                    color="primary"
                                    href="https://www.instagram.com/"
                                >
                                    <v-avatar>
                                        <img
                                            src="../../src/assets/instagram.png"
                                        />
                                    </v-avatar>
                                </v-btn>
                            </div>
                        </v-col>
                    </v-row>
                </v-container>
            </v-form>

            <!--   <div>
      <Map class="map"/>
    </div>  	
  -->
        </v-app>
    </div>
</template>

<script>
let emailjs = require('emailjs-com');

//import Map from "@/components/Map";

export default {
    name: 'contact',
    //components: {
    // Map
    // },

    data: () => ({
        valid: true,
        from_fname: '',
        from_fnameRules: [
            v => !!v || 'Name is required',
            v => (v && v.length > 2) || 'Please enter a valid name'
        ],
        from_lname: '',
        from_lnameRules: [
            v => !!v || 'Last Name is required',
            v => (v && v.length > 2) || 'Please enter a valid name'
        ],
        from_email: '',
        from_emailRules: [
            v => !!v || 'Email address is required',
            v => /.+@.+/.test(v) || 'Please enter an email address'
        ],
        message: '',
        messageRules: [v => !!v || 'Please complete email and message'],
        alert: false,
        loader: null,
        loading: false
    }),

    //dar tiempo limitado

    watch: {
        loader() {
            const l = this.loader;
            this[l] = !this[l];
            this.alert = true;
            setTimeout(() => (this[l] = false), 3000);

            this.loader = null;
        }
    },

    created() {
        emailjs.init('user_TbIoJYmotWxlhp4YZfP0e');
    },

    methods: {
        // validations
        submit() {
            let data = {
                from_fname: this.from_fname,
                from_lname: this.from_lname,
                from_email: this.from_email,
                message: this.message
            };

            if (this.$refs.form.validate()) {
                console.log('Sending...');
                emailjs.send('gmail', 'dentalclinic', data).then(
                    function(Response) {
                        if (Response.text === 'OK') {
                            //alert("email had sended successfully");
                        }
                        console.log(
                            'SUCCESS. status=%d, text=%s',
                            Response.status,
                            Response.text
                        );
                    },
                    function(err) {
                        alert('Message faild');
                        console.log('FAILED. error=', err);
                    },
                    this.$refs.form.reset()
                );
            }
        },

        clear() {
            this.$refs.form.reset();
        }
    }
};
</script>

<style lang="scss" scoped>
.map {
    height: 400px;
}
</style>
