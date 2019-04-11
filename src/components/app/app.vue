<template>
   <v-app>
      <div v-if="$vuetify.breakpoint.mdAndDown">
         <v-toolbar flat fixed scroll-off-screen class="white">
            <v-layout justify-center>
               <span class="primary--text title">Business Name</span>
            </v-layout>
         </v-toolbar>
         <v-bottom-nav class="elevation-0" :active.sync="bottomNav" :value="true" fixed>
            <v-btn  v-for="item in menuItems" :key="item.title" color="teal" flat :value="item.title" :to="item.path">
               <span>{{item.title}}</span>
               <v-icon>{{item.icon}}</v-icon>
            </v-btn>
         </v-bottom-nav>
      </div>
      <v-toolbar flat fixed scroll-off-screen v-else class="white">
         <v-layout justify-center>
            <v-toolbar-items>
               <v-btn flat color="primary" v-for="item in menuItems" :key="item.title" :to="item.path">{{item.title}}</v-btn>
            </v-toolbar-items>
         </v-layout>
      </v-toolbar>
      <v-content>
         <v-slide-x-transition mode="out-in">
            <router-view></router-view>
         </v-slide-x-transition>
      </v-content>
   </v-app>
</template>
<script src="./app.ts"></script>