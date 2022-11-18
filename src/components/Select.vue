<script>

import {store} from '../data/store';

export default {
  name: 'Select',
  data(){
    return{
      store
    }
  }
}
</script>

<template>
  <div class="container">
      <select @change="$emit('changeSeries')" v-model="store.seriesSearch" class="form-select my-4">
          <option value="" selected>Select Category</option>
          <option value="breaking bad">Breaking Bad</option>
          <option value="better call saul">Better Call Saul</option>
      </select>
  </div>
</template>

<style lang="scss" scoped>

</style>