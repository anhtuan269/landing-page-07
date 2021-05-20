<template>
  <div class="avatar">
      <div class="image">
          <img :src="item.url" :alt="item.alt">
      </div>
      <div class="info">
          <h4>{{item.name}}</h4>
          <p>{{item.share}}</p>
      </div>
      <div class="rate">
          <p>{{item.commit}}</p>
          <img :src="item.star" alt="">
          <p>{{item.rate}}</p>
      </div>

  </div>
</template>

<script>
export default {
    components:{

    },
    props: {
        item:{
            type:Object
        }
    }

}
</script>

<style>

</style>