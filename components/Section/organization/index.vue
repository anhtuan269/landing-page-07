<template>
  <div class="organizatios mb-20 max-w-400 mx-auto md:max-w-2xl xl:max-w-1200 xl:flex xl:justify-between xl:items-center acer:max-w-1280 2xl:max-w-1460">
    <div class="head mb-20 xl:w-670 2xl:w-700  ">
      <img src="@/static/image/arow.png" alt="" class="mb-4 w-20" />
      <Heading
        v-for="(head, index) in heading"
        :key="index"
        v-show="head.type === 'organization'"
        :section="head.type"
        :head="head"
      />
    </div>
    <div class="mem relative mx-auto md:w-400 xl:ml-auto xl:mx-0  xl:w-525 2xl:w-610">
      <div class="content border-4 border-solid border-black rounded-2xl pt-8 pl-10 max-w-380 mr-auto  bg-white md:mx-auto xl:max-w-460 xl:ml-auto 2xl:max-w-610 ">
        <h3 class="text-28 font-bold leading-10 mb-10">Members</h3>
      <Member
        v-for="(item, index) in avatar"
        :key="index"
        v-show="item.type === 'member'"
        :item="item"
        :type="item.type"
      />
      </div>
      <div class="bg-green-01 h-full w-380 rounded-2xl absolute top-4   right-1 z-a md:-right-1 xl:w-460 xl:right-2 2xl:w-610 2xl:-right-4" ></div>
    </div>
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
      avatar: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
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