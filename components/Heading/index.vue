<template>
  <div class="heading">
      <h2 class="title">{{head.title}}</h2>
      <p>{{head.description}}</p>
  </div>
</template>

<script>
export default {
    props: {
        head:{
            type:Object
        }
    }

}
</script>

<style>

</style>