<template>
  <div class="investor-card">
      <img :src="item.url" alt="">
      <h5>{{item.name}}</h5>
      <p>{{item.pre}}</p>
      <p>{{item.description}}</p>
      <h3>{{item.commit}}</h3>
      <p>{{item.dai}}</p>
      <h3>{{item.share}}</h3>
      <p>{{item.num}}</p>

  </div>
</template>

<script>
export default {
    props: {
        item:{
            type:Object
        }
    }

}
</script>

<style>

</style>