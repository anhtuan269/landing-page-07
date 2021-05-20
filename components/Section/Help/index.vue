<template>
  <div class="help-center mb-20 max-w-400 mx-auto md:max-w-2xl xl:max-w-1200  acer:max-w-1280 2xl:max-w-1460">
    <Heading
    class="xl:w-at-02 xl:mx-auto xl:text-center"
      v-for="(head, index) in heading"
      :key="index"
      :head="head"
      v-show="head.type === 'help'"
      :section="head.type"
    />
   <div class="card-center xl:flex xl:items-center xl:justify-between">
      <div
      class="feature-card px-10 py-8 bg-white rounded-2xl shadow-lg hover:shadow-xl border border-solid mt-20 cursor-pointer transform hover:scale-105 duration-300 ease-linear xl:w-380 xl:h-n-270 acer:w-400 2xl:w-460 "
    >
      <Heading
      class=""
        v-for="(head, index) in heading"
        :key="index"
        :head="head"
        v-show="head.type === 'model'"
        :section="head.type"
      />
      <Mini
        v-for="(item, index) in mini"
        :key="index"
        v-show="item.type === 'model'"
        :type="item.type"
        :item="item"
      />
    </div>
    <div class="feature-card  px-10 py-8 bg-white rounded-2xl shadow-lg hover:shadow-xl border border-solid mt-20 cursor-pointer transform hover:scale-105 duration-300 ease-linear xl:w-380 xl:h-n-270 acer:w-400 2xl:w-460">
      <Heading
        v-for="(head, index) in heading"
        :key="index"
        :head="head"
        v-show="head.type === 'FAQ'"
        :section="head.type"
      />
      <Mini
        v-for="(item, index) in mini"
        :key="index"
        v-show="item.type === 'FAQ'"
        :type="item.type"
        :item="item"
      />
    </div>
    <div class="feature-card  px-10 py-8 bg-white rounded-2xl shadow-lg hover:shadow-xl border border-solid mt-20 cursor-pointer transform hover:scale-105 duration-300 ease-linear xl:w-380 xl:h-n-270 acer:w-400 2xl:w-460">
      <Heading
        v-for="(head, index) in heading"
        :key="index"
        :head="head"
        v-show="head.type === 'video'"
        :section="head.type"
      />
      <Mini
        v-for="(item, index) in mini"
        :key="index"
        v-show="item.type === 'video'"
        :type="item.type"
        :item="item"
      />
    </div>
   </div>
    <Button
      v-for="(item, index) in button"
      :key="index"
      v-show="item.type === 'more'"
      :item="item"
      :background="item.type"
    />
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import Mini from "@/components/Mini_button";
import Button from "@/components/Button";
export default {
  components: {
    Heading,
    Mini,
    Button,
  },
  data() {
    return {
      heading: [],
      mini: [],
      button: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
    this.mini = await fetch("http://localhost:3000/mini_button").then((res) => {
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