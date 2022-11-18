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
  },
  computed:{
    getResult(){
      return store.characterList.length
    }
  }
}
</script>

<template>
  <div class="container h-100 my-4">
    <div class="row">
      <div class="col-12">
        <p>
          Trovati {{ getResult }} personaggi
        </p>
      </div>
    </div>
  
      <div v-if="store.isLoaded" class="row h-100 p-4 row-list">
        <CharacterCard  
        v-for="character in store.characterList"
        :key="character.id"
        :character="character"/>
      </div>
      <div class="loading" v-else>
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
  .col-12{
    background-color: #0f6432;
    padding-top: 10px;
    color: white;
    font-size: 1.3rem;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .loading{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
  }
</style>