<template>
  <div class="footer flex justify-between mb-20">
      <Logo v-for="(item,index) in logo " :key="index" :item="item" v-show="item.type==='footer'"/>
     <div class="flex">
          <Menu v-for="(item,index) in menu " :key="index" :item="item" v-show="item.type==='footer'" />
  </div>
     </div>
</template>

<script>
import Logo from '@/components/Logo'
import Menu from '@/components/Menu'
export default {
    components: {
        Logo,
        Menu
    },
    data() {
        return{
            logo:[],
            menu:[]
        }
    },
    async fetch() {
        this.logo = await fetch('http://localhost:3000/logo').then((res) => {
            return res.json()
        });
        this.menu = await fetch('http://localhost:3000/menu').then((res) => {
            return res.json()
        })
    }


}
</script>

<style>

</style>