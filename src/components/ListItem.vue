<template>
  <div class="card-body">
    <!-- <h5 class="card-title">{{ elem.title }}</h5> -->
    <img :src = "require('@/assets/'+ elem.img +'')"/> 
   <!--  <img src = "../assets/slider_01.jpg"/> -->
    <p class="card-text">
      {{elem.text}}
    </p>
  </div>
</template>

<script>
export default {
  props: ["elem", "index"],
  computed:{
  }
};
</script>
<style lang="scss" scoped>
  .card-body{
    min-width:100px;
    max-width:200px;
    min-height:260px;
    margin:0 auto;
    padding:5px 10px;
    background-color:white;
    border-radius: 3px;
    box-shadow: 0px 2px 6px rgb(56, 56, 56);
  }
  img{
    display:block;
    margin:0 auto;
    max-width:135px;
    max-height:140px;
  }
</style>
