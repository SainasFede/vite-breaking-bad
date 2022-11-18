<script>

import axios from 'axios'
import {store} from '../src/data/store'
import AppHeader from './components/AppHeader.vue';
import CharacterList from './components/CharacterList.vue';
import Select from './components/Select.vue';

export default {
  name: 'App',
  data(){
    return{
      store
    }
  },
  components:{
    AppHeader,
    CharacterList,
    Select
  },
  methods:{
    getCharacter(){
      store.isLoaded = false;
      axios.get(store.apiUrl, {
        params: {
          category: store.seriesSearch
        }
      })
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
<Select  @changeSeries="getCharacter()"/>
<CharacterList/>

</template>

<style lang="scss">

  @use './styles/general.scss'

</style>