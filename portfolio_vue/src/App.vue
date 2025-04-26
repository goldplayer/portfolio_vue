<script setup>
import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
import HomeView from './views/HomeView.vue';
import { CircleX } from 'lucide-vue-next';
import { ref } from 'vue'

const menu_action = ref(false)

</script>

<template>
  <header class="container">
    <div class="row">
      <div class="col-6 col-sm-6 col-md-6 ">
        <div class="logo">
          <h2 class="text-logo">Porgher.studio</h2>
        </div>
      </div>
      <div class="col-6 col-sm-6 col-md-6  text-end">
        <div class="burger-menu">
          <button class="burger-button" @click="menu_action=true">
              <span class="burger-lines"></span>
              <span class="burger-lines"></span>
              <span class="burger-lines"></span>
          </button>


          <div v-if="menu_action" class="menu-overlay">
              <button class="close" @click="menu_action=false">
                <CircleX />
              </button>


              <nav class="menu">
                <router-link to="/" @click="open=false">Home</router-link>
                <router-link to="/abut" @click="open=false">About</router-link>
                <router-link to="/gallery" @click="open=false">Gallery</router-link>
              </nav>
          </div>
        </div>
      </div>
    </div>
  </header>



  <div class="container">
    <RouterView />
  </div>


  
</template>



