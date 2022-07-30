<template>

 <div class="dashboard">
 <h1 class="subheading grey--text">Dashboard</h1>
 <v-container class="my-5">

  <v-layout row class="mb-3">


<v-tooltip top>
      <template v-slot:activator="{ on, attrs }">
    <v-btn small flat color="grey" @click="sortBy('title')" v-on="on">
      <v-icon left small>mdi-folder</v-icon>
      <span class="caption text-lowercase">By project name </span>
    </v-btn>
     </template>
      <span>Top tooltip</span>
    </v-tooltip>
    
    <v-tooltip top>
      <template v-slot:activator="{ on, attrs }">
    <v-btn small flat color="grey" @click="sortBy('person')"  v-on="on">
      <v-icon left small>mdi-person</v-icon>
      <span class="caption text-lowercase">By person </span>
    </v-btn>
     </template>
      <span>Top tooltip</span>
    </v-tooltip>
    
  </v-layout>

  <v-card flat class="pa-3" v-for="project in Projects " :key="project.title">
    <v-layout row wrap :class="`pa-3 project ${project.status}` ">
      <v-flex xs12 md6>
        <div class="caption grey--text  "> Project Title</div>
        <div>{{project.title}}</div>
      </v-flex>

      <v-flex xs6 sm4 md2>
         <div class="caption grey--text  "> Person</div>
         <div>{{project.person}}</div>
      </v-flex>

      <v-flex xs6 sm4 md2>
         <div class="caption grey--text  "> Due by</div>
         <div>{{project.due}}</div>
      </v-flex>

      <v-flex xs2 sm4 md2>
        <!-- <div class="caption grey--text  "> Status</div>
         <div>{{project.status}}</div> -->
         <div class="right"></div>
         <v-chip small :class="`${project.status} white--text caption my-2`">{{project.status}}</v-chip>
      </v-flex>
    </v-layout>
    <v-divider></v-divider>
  </v-card>


 </v-container>
  <!--      v-btn class="hidden-md-and-down">click me</v-btn> -->

   <!--v-btn class="hidden-md-and-up">click me</!--v-btn> -->
   <!--v-btn class="hidden-sm-only">click me</!--v-btn> -->
 </div>
</template>

<script>
  export default{
    data(){
      return{
        Projects:[
        {title:'Design a new website', person:'The Net Ninja', due:'31st Aug 2022', status:'ongoing'},
        {title:'code up the homepage', person:'Tejal', due:'30st Aug 2022', status:'complete'},
        {title:'Design video', person:' Ninja', due:'31st mar 2022', status:'overdue'},
        {title:'create community forum', person:' Net Ninja', due:'31st july 2022', status:'ongoing'}
        ]
      }
    },
    methods: {
      sortBy(prop){
        this.Projects.sort((a,b) => a[prop] < b[prop] ? -1:1)
      }
    }

  }
</script>
<style>
.project.complete{
  border-left:4px solid blue
}
.project.overdue{
  border-left:4px solid orange
}.project.ongoing{
  border-left:4px solid tomato
}
.v-chip.complete{
  background:blue !important;
}
.v-chip.overdue{
  background: orange !important;
}
.v-chip.ongoing{
  background:tomato !important;
}
</style>
