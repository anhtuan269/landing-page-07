<template>
  <div class="open max-w-400 mx-auto md:max-w-2xl xl:max-w-1200 xl:flex xl:items-center xl:justify-between ">
    <div class="head xl:w-6/12">
      <Heading
        v-for="(head, index) in heading"
        :key="index"
        :head="head"
        v-show="head.type === 'start'"
        :section="head.type"
      />
      <Button
        class="text-center my-12 xl:text-left xl:mt-12 xl:my-0"
        v-for="(item, index) in button"
        :key="index"
        v-show="item.type === 'early'"
        :item="item"
        :background="item.type"
      />
    </div>
   <div class="image xl:w-6/12">
      <img src="@/static/image/footer.png" alt="" class="w-full " />
   </div>
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import Button from "@/components/Button";
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