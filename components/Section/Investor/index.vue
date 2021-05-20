<template>
  <div class="investor mb-20">
      <Investor v-for="(item,index) in investor" :key="index" :item="item" />
      <Button  v-for="(item,index) in button" :key="index" :item="item" v-show="item.type==='vote'" />
      <img src="@/static/image/cycle.png" alt="">
      <Heading  v-for="(head,index) in heading" :key="index" :head="head"  v-show="head.type==='investor'"/>
  </div>
</template>

<script>
import Investor from '@/components/Investor'
import Button from '@/components/Button'
import Heading from '@/components/Heading'
export default {
    components: {
        Investor,
        Button,
        Heading
    },
    data() {
        return {
            heading:[],
            button:[],
            investor:[]
        }
    },
    async fetch() {
        this.heading = await fetch('http://localhost:3000/heading').then((res) => {
            return res.json()
        });
        this.button = await fetch('http://localhost:3000/button').then((res) => {
            return res.json()
        });
        this.investor = await fetch('http://localhost:3000/inventor').then((res) => {
            return res.json()
        })
    }


}
</script>

<style>

</style>