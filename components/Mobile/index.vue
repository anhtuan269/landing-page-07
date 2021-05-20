<template>
  <div class="mobile">
    <ul class="menu">
      <li
        class="hover:text-green-01 duration-300 ease-linear text-20 leading-7 font-medium mb-3"
      >
        <nuxt-link :to="item.link">{{ item.text }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
    },
    type: {
      type: String,
    },
  
  },
};
</script>

<style >
 a.nuxt-link-exact-active {
        color:#71A894;
    }
</style>