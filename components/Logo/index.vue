<template>
  <div class="logo">
      <img :src="item.url" :alt="item.alt" class="mx-auto">
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