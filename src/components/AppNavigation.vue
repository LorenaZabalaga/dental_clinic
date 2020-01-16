<template>
    <span>


      <v-navigation-drawer fixed app v-model="drawer" class="teal lighten-3" dark disable-resize-watcher>


      <v-list>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.url"
          link
        >
          <v-list-item-icon>
            <v-icon>mdi-{{item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>


    </v-navigation-drawer>




        <v-toolbar app color="white">
        <v-app-bar-nav-icon class= "hidden-md-and-up" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>            
            <v-toolbar-side-icon
                class="hidden-md-and-up"
                @click="drawer = !drawer"
            ></v-toolbar-side-icon>

            <v-spacer class="hidden-md-and-up"></v-spacer>

            <router-link to="/">
                <v-toolbar-title to="/" class="teal--text mr-4">{{       
                    appTitle
                }}</v-toolbar-title>
            </router-link>
        <v-toolbar-items>   
            <v-btn text color="teal" extended class="hidden-sm-and-down" to="/">HOME</v-btn>
            <v-btn
                text
                color="teal"
                class="hidden-sm-and-down"
                to="/products"
                >PRODUCTS</v-btn
            >
        </v-toolbar-items>

            <v-spacer class="hidden-sm-and-down"></v-spacer>

        <v-toolbar-items>    
            <v-btn text color="teal" class="hidden-sm-and-down" to="/about">ABOUT</v-btn>
            <v-btn text color="teal" class="hidden-sm-and-down" to="/contact">CONTACT</v-btn>
        </v-toolbar-items>

        </v-toolbar>

        <v-footer color="white" app inset>
          <span class="teal--text">&copy; Z&Z.FunCode 2020</span>
        </v-footer>  

    </span>
</template>

<script>
export default {
    name: 'AppNavigation',
    data() {
        return {
            appTitle: 'Dental Clinic',
            drawer: false,
            items: [
                { title: 'Home', url: '/', icon: 'home-city' },
                { title: 'Products', url: '/products', icon: 'tooth' },
                { title: 'About', url: '/about', icon: 'information'},
                { title: 'Contact', url: '/contact', icon: 'contact-phone'}
            ]

        };
    }
};
</script>

<style scoped>
a {
    color: teal;
    text-decoration: none;
}
</style>




