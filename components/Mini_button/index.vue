<template>
  <div class="button "
  :class="mini">
      <button class="py-1 px-2 bg-green-01 rounded-at-02 text-white text-16 leading-6 font-medium">{{item.text}}</button>
      <h3>{{item.apply}}</h3>
  </div>
</template>

<script>
export default {
    props:{
        item:{
            type:Object
        },
        type: {
            type: String
        }
    },
    computed: {
        mini () {
            if(this.type==='share') {
                return ''
            } else{
                return 'flex items-center justify-between  mt-5'
            }
        }
    }

}
</script>

<style>

</style>