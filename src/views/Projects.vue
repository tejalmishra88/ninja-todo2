<template>

 <div class="projects">
 <h1 class="subheading grey--text">Projects</h1>

 

 <v-container class="my-5">
   <v-expansion-panels>
    <v-expansion-panel
      v-for="(item,i) in myProjects"
      :key="i"
    >
      <v-expansion-panel-header >
        new task
      </v-expansion-panel-header>
    <div slot="header">{{item.title}}</div>
      <v-card-text class="px-4 grey--text"></v-card-text>
      <div class="font-weight-bold">due by {{item.due}}</div>
      <v-expansion-panel-content>
       {{item.title}} xyxxxxx
      </v-expansion-panel-content>
    </v-expansion-panel>
  </v-expansion-panels>

 

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
         projects:[
        {title:'Design a new website', person:'The Net Ninja', due:'31st Aug 2022', status:'ongoing'},
        {title:'code up the homepage', person:'Tejal', due:'30st Aug 2022', status:'complete'},
        {title:'Design video', person:' Ninja', due:'31st mar 2022', status:'overdue'},
        {title:'create community forum', person:' Net Ninja', due:'31st july 2022', status:'ongoing'},
         {title:'Design a new website..again', person:'The Net Ninja', due:'31st Aug 2022', status:'ongoing'},
        ]
      }
    },
    computed:{
      myProjects(){
        return this.projects.filter(project => { return project.person=== 'The Net Ninja'})
      }
    }
  }
</script>