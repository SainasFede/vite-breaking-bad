<script>
export default {
  name: 'CharacterCard',
  props:{
    character: Object
  }
}
</script>

<template>
  <div class="card m-2 p-3" style="width: 18rem;">
  <img :src="character.img" alt="character.name">
  <div class="card-body">
    <h5 class="card-title">{{character.name}}</h5>
    <p>{{character.nickname}}</p>
    <p>{{character.status}}</p>
  </div>
</div>
</template>


<style lang="scss" scoped>
  .card{
    width: calc(100% / 5);
    text-align: center;
    background-color: rgba(46,58,70,255);
    img{
      width: 100%;
      object-fit: cover;
    };
    .card-body{
      background-color: #0f6432;
    }
    h5{
      color: white;
    };
    p{
      color: #6e716d;
    }
  }
</style>