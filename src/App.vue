<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>
      <div class="wrapper">

          <nav class="navbar navbar-expand-lg navbar-light bg-light">
            <div class="container">
              <a class="navbar-brand" href="#"><strong>Al Quran</strong></a>

              <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon"></span>
              </button>
              <div class="collapse navbar-collapse" id="navbarSupportedContent">
              <ul class="navbar-nav">
              <li class="nav-item active col-6"><router-link class="nav-link" to="/home">Home</router-link></li>
              <li class="nav-item active col-6"><router-link class="nav-link" to="search">Search</router-link></li>
              <li class="nav-item active col-6"><router-link class="nav-link" to="/surah">Surat</router-link></li>
              <li class="nav-item active col-6"><router-link class="nav-link" to="/ayat">Ayat</router-link></li>
 
              </ul>
            </div>
           </div>
          </nav>



      </div>
  </header>

  <RouterView />
</template>

