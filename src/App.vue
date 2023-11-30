<script setup>
import{RouterView} from "vue-router"
//import HomeView from "./views/HomeView.vue"
//import AboutView from "./views/AboutView.vue"
import Nav from "./components/Nav.vue"
//import {ref} from "vue"
//const randomState = ref("")
</script>

<template>
    <div>
    <!-- {{randomState}} 
    <button @click="randomState='hello there'">Click Me!!</button>
    -->
    <Nav/>
        <RouterView/>

     <!--
        
            <HomeView/>
        <AboutView/>

        -->
    </div>
</template>