<template>
  <div class="organizatios mb-20">
    <img src="@/static/image/arow.png" alt="" />
    <Heading v-for="(head,index) in heading" :key="index" v-show="head.type==='organization'" :section="head.type" :head="head" />
    <h3>Members</h3>
    <Member v-for="(item, index) in avatar" :key="index" v-show="item.type==='member'" :item="item"  />
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import Member from "@/components/Avatar";
export default {
  components: {
    Heading,
    Member,
  },
  data() {
    return {
      heading: [],
      avatar:[]
    };
  },
  async fetch() {
    this.heading = await fetch('http://localhost:3000/heading').then((res) => {
      return res.json()
    });
    this.avatar = await fetch('http://localhost:3000/avatar').then((res) => {
      return res.json()
    })
  }
};
</script>

<style>
</style>