<template>
  <div class="investor mb-20 max-w-400 mx-auto flex flex-col-reverse md:max-w-2xl xl:flex-row xl:max-w-1200 xl:justify-between acer:max-w-1280 2xl:max-w-1460">
    <div
      class="box mt-16 border-4 border-black rounded-2xl px-10 py-9 bg-white md:w-400 md:mx-auto xl:mx-0 xl:mr-auto 2xl:w-610 "
    >
      <Investor v-for="(item, index) in investor" :key="index" :item="item" />
      <Button
        v-for="(item, index) in button"
        :key="index"
        :item="item"
        v-show="item.type === 'vote'"
        :background="item.type"
      />
    </div>
    <div class="head xl:w-670">
      <img src="@/static/image/cycle.png" alt="" class="w-20 mb-6" />
      <Heading
        v-for="(head, index) in heading"
        :key="index"
        :head="head"
        v-show="head.type === 'investor'"
        :section="head.type"
      />
    </div>
  </div>
</template>

<script>
import Investor from "@/components/Investor";
import Button from "@/components/Button";
import Heading from "@/components/Heading";
export default {
  components: {
    Investor,
    Button,
    Heading,
  },
  data() {
    return {
      heading: [],
      button: [],
      investor: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
    this.button = await fetch("http://localhost:3000/button").then((res) => {
      return res.json();
    });
    this.investor = await fetch("http://localhost:3000/inventor").then(
      (res) => {
        return res.json();
      }
    );
  },
};
</script>

<style>
</style>