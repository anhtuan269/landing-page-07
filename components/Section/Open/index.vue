<template>
  <div class="open">
    <Heading 
     v-for="(head, index) in heading"
      :key="index"
      :head="head"
      v-show="head.type === 'start'"
      :section="head.type"
    />
    <Button
    v-for="(item, index) in button"
      :key="index"
      v-show="item.type === 'early'"
      :item="item"
    />
    <img src="@/static/image/footer.png" alt="" />
  </div>
</template>

<script>
import Heading from '@/components/Heading'
import Button from '@/components/Button'
export default {
  components: {
    Heading,
    Button,
  },
  data() {
    return {
      heading: [],
      button: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
   
    this.button = await fetch("http://localhost:3000/button").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>