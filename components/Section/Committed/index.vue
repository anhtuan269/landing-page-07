<template>
  <div class="committed mb-20">
      <div class="left">
          <img src="@/static/image/blue-icon.png" alt="">
          <Heading v-for="(head, index) in heading" :key="index" :head="head" :section="head.type" v-show="head.type==='commited'" />
      </div>
      <div class="right">
          <div class="write">
              <Heading v-for="(head, index) in heading" :key="index" :head="head" :section="head.type" v-show="head.type==='share'" />
              <Mini v-for="(item,index) in mini" :key="index" v-show="item.type==='share'" :item="item"/>
          </div>
          <div class="aplicants">
              <h3>3 aplicants</h3>
              <Avatar  v-for="(item,index) in avatar" :key="index" v-show="item.type==='applicants'" :item="item" />
          </div>
          <div class="alex">
              <Avatar v-for="(item,index) in avatar" :key="index" v-show="item.type==='view'" :item="item"  />
              <Button v-for="(item,index) in button" :key="index" v-show="item.type==='more'" :item="item"  />

          </div>
      </div>
  </div>
</template>

<script>
import Heading from '@/components/Heading'
import Mini from '@/components/Mini_button'
import Button from '@/components/Button'
export default {
    components: {
        Heading,
        Mini,
        Button
    },
    data() {
        return {
            heading:[],
            button:[],
            mini:[],
            avatar:[]
        }
    },
    async fetch() {
        this.heading = await fetch('http://localhost:3000/heading').then((res) => {
            return res.json()
        });
        this.mini = await fetch('http://localhost:3000/mini_button').then((res) => {
            return res.json()
        });
        this.button = await fetch('http://localhost:3000/button').then((res) => {
            return res.json()
        });
        this.avatar = await fetch('http://localhost:3000/avatar').then((res)=> {
            return res.json()
        })
    }
}
</script>

<style>

</style>