<template>
  <div class="heading">
    <h2 class="title tracking-wider" :class="heading">{{ head.title }}</h2>
    <p :class="description">{{ head.description }}</p>
  </div>
</template>

<script>
export default {
  props: {
    head: {
      type: Object,
    },
    section: {
      type: String,
    },
  },
  computed: {
    heading() {
      if (this.section === "hero") {
        return " text-42 font-extrabold leading-l-50 xl:text-64 xl:leading-l-80 xl:";
      } else if (this.section === "feature") {
        return "text-28  font-extrabold  leading-l-40 xl:text-48 xl:leading-l-60 ";
      } else if (this.section === "organization") {
        return "text-28  font-extrabold  leading-l-40  xl:text-48 xl:leading-l-60";
      } else if (this.section === "investor") {
        return "text-28  font-extrabold  leading-l-40  xl:text-48 xl:leading-l-60";
      } else if (this.section === "commited") {
        return "text-28  font-extrabold  leading-l-40  xl:text-48 xl:leading-l-60";
      } else if (this.section === "help") {
        return "text-28  font-extrabold  leading-l-40  xl:text-48 xl:leading-l-60";
      } else if (this.section === "start") {
        return "text-28  font-extrabold  leading-l-40  xl:text-48 xl:leading-l-60";
      } else {
        return "text-16 font-bold leading-6";
      }
    },
    description() {
      if (this.section === "hero") {
        return "mt-10 text-18 leading-6 text-gray-01 xl:text-24 xl:leading-8  ";
      } else if (this.section === "share") {
        return "mt-4 text-16 leading-6 font-sermibold xl:text-18 leading-7 ";
      } else if (this.section === "modern") {
        return "mt-2 text-16 leading-6 font-sermibold xl:text-18 xl:leading-7";
      } else if (this.section === "design") {
        return "mt-2 text-16 leading-6 font-sermibold xl:text-18 xl:leading-7";
      } else if (this.section === "resilience") {
        return "mt-2 text-16 leading-6 font-sermibold xl:text-18 xl:leading-7";
      } else if (this.section === "start") {
        return "mt-2 text-16 leading-6 font-sermibold xl:text-18 xl:leading-7";
      } else {
        return " mt-6 text-16 leading-7  ";
      }
    },
  },
};
</script>

<style>
</style>