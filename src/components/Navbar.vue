<template>
<Nav>
<v-app-bar clipped-left text app>
    <v-app-bar-nav-icon class="grey--text" @click="drawer =!drawer"></v-app-bar-nav-icon>
        <v-app-bar-title class="text-uppercase grey-text">
        <span class="font-weight-light">Todo</span>  
        <span>Ninja</span>  

    </v-app-bar-title>
    <v-spacer></v-spacer>

    
    <!--dropdown-->
    <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="primary"
          dark
          v-bind="attrs"
          v-on="on"
        >
    <V-icon left> mdi-expand more</V-icon>
        <span>Menu</span>
        </v-btn>
        </template>
         <v-list>
        <v-list-item
          v-for="(item, index) in links"  :key="index"  >
          <v-list-item-title>{{ item.text }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
    <!----->

        <v-btn text color="grey">
            <span>sign out</span>
            <v-icon right>mdi-arrow-right-bold-box </v-icon>
        </v-btn>
</v-app-bar>

<v-navigation-drawer  bottom temporary clipped absolute dark
       v-model="drawer"  class="primary">

       <v-layout coloum justify-center pl-10>
        <v-flex class="mt-5">
            <v-avatar size="100">
                <img src="/avatar-5.png" alt="">
            </v-avatar>
            <p class="white--text subheading mt-1"> Tejal</p>
        </v-flex>
        <v-flex>
            <popup />
        </v-flex>  
       </v-layout>
   <v-list>
    <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
        <v-list-item-icon>
            <v-icon class="">{{link.icon}} </v-icon>
        </v-list-item-icon>
       <v-list-item-content>
        <v-list-item-title class="white--text">{{link.text}} </v-list-item-title>
       </v-list-item-content> 
    </v-list-item> 
   </v-list>   
</v-navigation-drawer>
</Nav>
</template>
   

<script>
import Popup from './popup.vue'

export default{
    components:{Popup},
    data(){
        return{
            drawer:false,
            links: [
                {icon:"mdi-grain", text:"dashboard", route:"/"},
                {icon:"mdi-folder", text:"my projects", route:"/projects"},
                {icon:"mdi-account-outline", text:"team", route:"/team"},
            ]
        }
    }
}
</script>