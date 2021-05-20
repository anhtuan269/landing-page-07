<template>
  <div class="feature mb-20 max-w-400 mx-auto md:max-w-2xl xl:max-w-1200">
    <Heading
      class=" xl:text-center xl:w-at-02 xl:mx-auto"
      v-for="(head, index) in heading"
      :key="index"
      :head="head"
      v-show="head.type === 'feature'"
      :section="head.type"
    />
    <div class="content mt-10 xl:flex xl:justify-between">
      <div class="feaeture-card text-center border cursor-pointer  px-6 py-16 rounded-sm shadow-lg  mb-16 hover:shadow-xl duration-300 ease-linear xl:w-380  ">
        <img src="@/static/image/Icon.png" alt="" class="mx-auto mb-6 w-20" />
        <Heading
          v-for="(head, index) in heading"
          :key="index" 
          :head="head"
          v-show="head.type === 'modern'"
          :section="head.type"
        />
      </div>
      <div class="feaeture-card text-center border px-6 py-16 rounded-sm shadow-lg  mb-16 hover:shadow-xl duration-300 ease-linear cursor-pointer xl:w-380">
        <img src="@/static/image/triangle.png" alt=""  class="mx-auto mb-6 w-20" />
        <Heading
          v-for="(head, index) in heading"
          :key="index"
          :head="head"
          v-show="head.type === 'design'"
          :section="head.type"
        />
      </div>
      <div class="feaeture-card text-center border px-6 py-16 rounded-sm shadow-lg  mb-16 hover:shadow-xl duration-300 ease-linear cursor-pointer xl:w-380">
        <img src="@/static/image/start.png" alt=""  class="mx-auto mb-6 w-20" />
        <Heading
          v-for="(head, index) in heading"
          :key="index"
          :head="head"
          v-show="head.type === 'resilience'"
          :section="head.type"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Heading from "@/components/Heading";
export default {
  components: {
    Heading,
  },
  data() {
    return {
      heading: [],
    };
  },
  async fetch() {
    this.heading = await fetch("http://localhost:3000/heading").then((res) => {
      return res.json();
    });
  },
};
</script>

<style>
</style>