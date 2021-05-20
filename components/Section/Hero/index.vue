<template>
  <div class="hero mb-40 max-w-400 mx-auto md:max-w-2xl md:mb-52  xl:max-w-1200 xl:flex xl:justify-between acer:max-w-1280 2xl:max-w-1460">
    <div class="left mb-10 md:mb-20  xl:w-610 xl:mt-20">
      <Heading class="mb-10" v-for="(head,index ) in heading" :key="index" :head="head" v-show="head.type==='hero'" :section="head.type" />
      <Button class="flex justify-center xl:justify-start" v-for="(item,index ) in button" :key="index" :item="item" v-show="item.type==='early'" :background="item.type"/>
    </div>
    <div class="right relative w-400 md:w-555 acer:w-610 2xl:w-680">
      <img src="@/static/image/hero-1.png" alt="" />
      <img src="@/static/image/hero-bg.png" alt="" class="absolute top-0 left-16 z-a w-310 md:w-555 2xl:left-24" />
    </div>
  </div>
</template>

<script>
import Heading from '@/components/Heading'
import Button from '@/components/Button'

export default {
    components: {
        Heading,
        Button
    },
    data() {
        return {
            heading:[],
            button:[]
        }
    },
    async fetch() {
        this.heading = await fetch('http://localhost:3000/heading').then((res)=> {
            return res.json()
        });
        this.button = await fetch('http://localhost:3000/button').then((res) => {
            return res.json()
        })
    }
};
</script>

<style>
</style>