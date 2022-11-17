<script>

import axios from 'axios'
import {store} from '../src/data/store'
import AppHeader from './components/AppHeader.vue';
import CharacterList from './components/CharacterList.vue';

export default {
  name: 'App',
  data(){
    return{
      store
    }
  },
  components:{
    AppHeader,
    CharacterList
  },
  methods:{
    getCharacter(){
      store.isLoaded = false;
      axios.get(store.apiUrl)
      .then( result => {
      store.characterList = result.data
      store.isLoaded = true;
    })
      .catch( error => {
      console.log(error);
    })
    }
  },
  mounted(){
    this.getCharacter();
  }
}
</script>


<template>
<AppHeader />
<CharacterList />

</template>

<style lang="scss">

  @use './styles/general.scss'

</style>