<template>

 <div class="projects">
 <h1 class="subheading grey--text">Projects</h1>

 

 <v-container class="my-5">
   <v-expansion-panels>
    <v-expansion-panel
      v-for="(item,i) in 5"
      :key="i"
    >
      <v-expansion-panel-header>
        projects
      </v-expansion-panel-header>
      <div class="font-weight-bold">due by xx.xx.xx</div>
      <v-expansion-panel-content>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
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
  export default{}
</script>