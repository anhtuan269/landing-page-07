<template>
  <div class="feature mb-20">
      <Heading v-for="(head, index) in heading" :key="index" :head="head" v-show="head.type==='feature'" :section="head.type"/>
      <div class="feaeture-card">
          <img src="@/static/image/Icon.png" alt="">
          <Heading v-for="(head, index) in heading" :key="index" :head="head" v-show="head.type==='modern'" :section="head.type" />

      </div>
       <div class="feaeture-card">
          <img src="@/static/image/triangle.png" alt="">
          <Heading v-for="(head, index) in heading" :key="index" :head="head" v-show="head.type==='design'" :section="head.type" />

      </div>
       <div class="feaeture-card">
          <img src="@/static/image/start.png" alt="">
          <Heading v-for="(head, index) in heading" :key="index" :head="head" v-show="head.type==='resilience'" :section="head.type" />

      </div>
  </div>
</template>

<script>
import Heading from '@/components/Heading'
export default {
    components: {
        Heading
    },
    data() {
        return {
            heading:[]
        }
    },
    async fetch() {
        this.heading = await fetch('http://localhost:3000/heading').then((res) => {
            return res.json()
        })
    }


}
</script>

<style>

</style>