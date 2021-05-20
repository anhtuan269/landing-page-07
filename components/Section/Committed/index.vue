<template>
  <div class="committed mb-20 max-w-400 mx-auto md:max-w-2xl xl:max-w-1200 xl:flex xl:justify-between xl:items-center">
    <div class="left xl:w-610 xl:-mt-10">
      <img src="@/static/image/blue-icon.png" alt="" class="w-20 mb-3" />
      <Heading
        v-for="(head, index) in heading"
        :key="index"
        :head="head"
        :section="head.type"
        v-show="head.type === 'commited'"
      />
    </div>
    <div class="right mt-20 xl:mt-0 xl:w-555">
      <div class="write relative xl:w-555 xl:mx-auto">
        <div
          class="share-box justify-between p-6 border-4 bg-white border-black rounded-2xl text-center mb-10 xl:w-555 xl:text-left xl:flex"
        >
          <Heading
            class="xl:w-380"
            v-for="(head, index) in heading"
            :key="index"
            :head="head"
            :section="head.type"
            v-show="head.type === 'share'"
          />
          <Mini
            class="mt-5 text-center xl:mt-0"
            v-for="(item, index) in mini"
            :key="index"
            v-show="item.type === 'share'"
            :item="item"
            :type="item.type"
          />
        </div>
        <div
          class="bg-green-01 w-at left-2 h-full absolute top-2 rounded-2xl z-a md:w-nt  "
        ></div>
      </div>
      <div class="avatar md:flex md:justify-between md:mt-10 ">
        <div
          class="aplicants border-black border-4 rounded-2xl px-10 py-8 bg-brown md:w-6/12 md:h-n-350 xl:w-330"
        >
          <h3 class="text-24 font-bold leading-8 mb-8">3 applicants</h3>
          <Avatar
            v-for="(item, index) in avatar"
            :key="index"
            v-show="item.type === 'applicants'"
            :item="item"
            :type="item.type"
          />
        </div>
        <div class="alex mt-16 border-4 border-green-01 rounded-2xl px-10 py-8 md:mt-10 md:w-5/12 md:h-n-350 xl:w-200 xl:px-5">
          <Avatar
            v-for="(item, index) in avatar"
            :key="index"
            v-show="item.type === 'view'"
            :item="item"
            :type="item.type"
          />
          <Button
            v-for="(item, index) in button"
            :key="index"
            v-show="item.type === 'profile'"
            :item="item"
            :background="item.type"
          />
        </div>
      </div>
    </div>
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
      button: [],
      mini: [],
      avatar: [],
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
    this.avatar = await fetch("http://localhost:3000/avatar").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>