<template>
    <div >
    <div>
      <v-app-bar
        color="#242424"
        dark
      >
        <v-icon class="mx-4">mdi-home</v-icon>
        <v-toolbar-title>sidonu</v-toolbar-title>
  
        <v-spacer></v-spacer>
  
        <v-toolbar-items>
          <v-btn text to="/signup"> Sign Up</v-btn>
          <v-btn text to="/signin"> Sign In</v-btn>
        </v-toolbar-items>
  
      </v-app-bar>
    </div>

    <v-content >
      <slot/>
    </v-content>

    <v-footer color="#242424" dark fixed>
      <v-spacer></v-spacer>
      <div>sidonu &nbsp;&nbsp; &copy; {{ new Date().getFullYear() }}</div>
      <v-spacer></v-spacer>
    </v-footer>
    </div>
</template>