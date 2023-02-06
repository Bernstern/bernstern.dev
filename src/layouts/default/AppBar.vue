<template>
  <v-app-bar prominent color="background">
    <v-container fluid class="align">
      <v-row class="ml-1">
        <v-icon class="mr-2 github-light-grey pa-2">mdi-book-outline</v-icon>
        <h2 class="repository-title">Bernstern</h2>
        <h2 class="github-light-grey pl-2 pr-2">/</h2>
        <h2 class="repository-title">Career</h2>
        <v-chip color="github-light-grey" class="ml-2" x-large
          ><h4 class="github-light-grey">Public</h4></v-chip
        >
        <v-spacer />
        <!-- TODO: Put a card that looks like the starred tab on a Github Repo that links to my Linkedin, could even have it get from my linkedin automatically to be the star count -->
        <!-- TODO: Decide whether watch, pin or fork would open a tab to send an email to me -->
      </v-row>
    </v-container>
  </v-app-bar>
</template>

<style scoped>
.repository-title {
  color: #549bf5;
}

.github-light-grey {
  color: #75838e;
}

.github-dark-grey {
  color: #454c56;
}
</style>

<script></script>
