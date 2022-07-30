<template>

 <div class="team">
 <h1 class="subheading blue--text">Team</h1>
 <v-container class="my-5">
  <v-layout row wrap>
    <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
    <v-card flat class="text-xs-center ma-3 ">
      <v-responsive class="pt-4 ggg">
        <v-avatar size="100" class="grey lighten-2">
          <img :src="person.avatar" alt="">
        </v-avatar>

      </v-responsive>
      <v-card-text>
        <div class="subheading tt" >{{person.name}}</div>
        <div class="grey--text vv">{{person.role}}</div>
      </v-card-text>
      <v-card-actions>
        <v-btn flat color="grey">
          <v-icon small left>mdi-email-outline</v-icon>
          <span>messege</span>
        </v-btn>
      </v-card-actions>
    </v-card> 
     </v-flex>
  </v-layout>
 </v-container>
  <!--v-btn class="hidden-md-and-down">click me</v-btn> -->

   <!--v-btn class="hidden-md-and-up">click me</!--v-btn> -->
   <!--v-btn class="hidden-sm-only">click me</!--v-btn> -->
 </div>
</template>

<script>
  export default{
    data(){
      return{
        team:[
         
          {name: 'The Net Ninja', role:'web developer', avatar:'/avatar-1.png'},
           {name: 'Tejal', role:'engineer', avatar:'/avatar-2.png'},
            {name: ' Ninja', role:'software developer', avatar:'/avatar-3.png'},
             {name: ' Net Ninja', role:'sales guru', avatar:'/avatar-4.png'},
        ]
      
        
      }
    }
  }
</script>
<style scoped>
.ggg{
  background-color: green;
}
.tt{
  background-color: aqua;
}
.vv{
  background-color: blueviolet;
}
</style>