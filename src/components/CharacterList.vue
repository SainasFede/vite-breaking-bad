<script>

import {store} from '../data/store'
import CharacterCard from './CharacterCard.vue';
import AppLoading from './AppLoading.vue';

export default {
  name: 'CharacterList',
  components:{
    CharacterCard,
    AppLoading
  },
  data(){
    return{
      store
    }
  }
}
</script>

<template>
  <div class="container my-4">

      <div class="row my-4">
        <div class="dropdown">
          <a class="btn btn-light dropdown-toggle" href="#" role="button"     data-bs-toggle="dropdown" aria-expanded="false">
          Select Category
          </a>

        <ul class="dropdown-menu">
          <li><a class="dropdown-item" href="#">Action</a></li>
          <li><a class="dropdown-item" href="#">Another action</a></li>
          <li><a class="dropdown-item" href="#">Something else here</a></li>
        </ul>
      </div>
      </div>
  
      <div v-if="store.isLoaded" class="row p-4 row-list">
        <div class="col-12 bg-secondary p-2">
          <h3>Found 62 characters</h3>
        </div>
        <CharacterCard  
        v-for="character in store.characterList"
        :key="character.id"
        :character="character"/>
      </div>
      <div v-else>
        <AppLoading />
      </div>

  </div>
</template>


<style lang="scss" scoped>
  .row-list{
    background-color: white;
    display: flex;
    justify-content: center;
  }
</style>