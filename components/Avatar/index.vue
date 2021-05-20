<template>
  <div class="avatar mb-10" :class="applicants">
    <div class="contact" :class="contact">
      <div class="image">
        <img :src="item.url" :alt="item.alt" />
      </div>
      <div class="info "
      :class="margin"
      >
        <h4 class="mb-1 leading-7 font-semibold" :class="size">
          {{ item.name }}
        </h4>
        <p class="text-14 text-gray-01 leading-7 font-medium">
          {{ item.share }}
        </p>
        <h3 class="text-gray-01 font-medium md:text-center">{{item.position}}</h3>
      </div>
    </div>
    <div class="rate items-center" :class="member">
      <p class="mb-5 md:mb-0">{{ item.commit }}</p>
     <div class="vote flex">
        <img :src="item.star" alt="" class="w-6 h-6 mr-4" />
      <p class="text-18 font-medium leading-5">{{ item.rate }}</p>
     </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  props: {
    item: {
      type: Object,
    },
    type: {
      type: String,
    },
  },
  computed: {
    margin() {
      if(this.type==='view') {
        return 'ml-4 md:ml-0 md:my-5'
      } else {
        return 'ml-4'
      }
    },
    contact() {
      if (this.type === "member") {
        return " flex items-center";
      } else if (this.type === "applicants") {
        return " flex items-center";
      } else {
        return " flex items-center md:flex-col" ;

      }
    },
    applicants() {
      if(this.type==="member") {
        return ''
      } else if (this.type === "applicants") {
        return " flex items-center justify-between";
      } else {
        return 'flex  justify-between items-center md:block '
      } 

    },
    member() {
      if (this.type === "member") {
        return " hidden";
      } else if(this.type === "applicants") {
        return " flex items-center";
      } else {
        return ' md:flex md:items-center md:justify-between'
      }
    },
    size() {
      if (this.type === "member") {
        return "text-22";
      } else {
        return "text-18";
      }
    },
  },
};
</script>

<style>
</style>