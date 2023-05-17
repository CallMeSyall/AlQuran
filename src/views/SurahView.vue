<template>
<br><br>
<div class="container">
<div class="card">
  <ul class="list-group list-group-flush text-center">
    <li class="text-center" v-for="(item,index) in daftarsurah">
    {{item.name_simple+" (" + item.name_arabic + ")"}}
      <p class="text-center" v-html = " daftarsurah[index].verses_count + ' ayat ' "></p>
      <router-link class="text-center" :to="{name: 'surahdetail', params: {id: item.id}}"><button type="button" class="btn btn-sm btn-primary">Baca</button></router-link>
      <hr>
    </li>
  </ul>
  </div>
  </div>
  </template>
  
  <script>
  import {ref} from "vue";
  import axios from "axios";
  export default {
      data() {
        return {
          daftarsurah: ref([])
        }
      },
      mounted() {
        this.getDaftarSurah()
      },
      methods: {
        getDaftarSurah() {
          axios.get("https://api.quran.com/api/v4/chapters?language=id")
              .then((respons) =>
              {
               console.log(respons)
                this.daftarsurah = respons.data.chapters
              })
              .catch((err) =>
              {
                console.log('error' + err)
              })
        }
      }
    }
  
  
  </script>
  
  <style scoped>
  li {
    list-style: none;
    text-align: left;
      padding-top: 80px;
  }
  
  
  </style>