<template>
  <div
    class="investor-card "
  >
    <div class="avatar flex items-center mb-5 ">
      <img :src="item.url" alt="" class="mr-3" />
      <div class="infor">
        <h5 class="text-20 leading-6 font-bold mb-2">{{ item.name }}</h5>
        <p class="text-gray-02 leading-6 font-semibold">{{ item.pre }}</p>
      </div>
    </div>
    <p class="text-14 leading-5 font-medium mb-5  ">{{ item.description }}</p>
    <div class="count flex items-center justify-start md:justify">
      <div class="commit mr-16">
        <h3 class="text-16 text-gray-02  font-medium leading-6 mb-3">{{ item.commit }}</h3>
        <p class=" text-20 leading-7 font-medium ">{{ item.dai }}</p>
      </div>
      <div class="share ">
        <h3 class="text-16 text-gray-02  font-medium leading-6 mb-3">{{ item.share }}</h3>
        <p class=" text-20 leading-7 font-medium ">{{ item.num }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
    },
  },
};
</script>

<style>
</style>