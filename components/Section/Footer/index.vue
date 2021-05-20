<template>
  <div class="footer  justify-between mt-20 mx-auto max-w-400 text-center pb-10 md:flex md:max-w-2xl xl:max-w-1200 acer:max-w-1280 2xl:max-w-1460">
      <Logo v-for="(item,index) in logo " :key="index" :item="item" v-show="item.type==='footer'" class="mx-auto md:mx-0" />
     <div class=" flex items-center justify-between">
          <Menu v-for="(item,index) in menu " :key="index" :item="item" v-show="item.type==='footer' " :type="item.type" class=" last:mr-0" />
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