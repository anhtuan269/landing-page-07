<template>
  <div class="button">
      <button>{{item.text}}</button>
      <h3>{{item.apply}}</h3>
  </div>
</template>

<script>
export default {
    props:{
        item:{
            type:Object
        }
    }

}
</script>

<style>

</style>