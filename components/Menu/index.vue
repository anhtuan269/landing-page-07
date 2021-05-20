<template>
  <ul class="menu ">
      <li class="hover:text-green-01 duration-300 ease-linear text-20 leading-7 font-medium"
      :class="margin"
      >
          <nuxt-link :to="item.link">{{item.text}}</nuxt-link>
      </li>
  </ul>
  
</template>

<script>
export default {
    props:{
        item: {
            type:Object
        },
        type: {
            type:String
        }
    },
    computed: {
        margin() {
            if(this.type==='footer') {
                return ' mt-10 md:mt-0 md:ml-5 xl:ml-10'
            } else {
                return 'mr-10'
            }
        }
    }

}
</script>

<style scoped>
    a.nuxt-link-exact-active {
        color:#71A894;
    }
</style>