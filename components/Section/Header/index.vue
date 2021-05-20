<template>
  <div
    class="header flex justify-between mb-20 items-center pt-10 max-w-400 mx-auto xl:max-w-1200 xl:mb-10 acer:max-w-1280 2xl:max-w-1460"
  >
    <Logo
      v-for="(item, index) in logo"
      :key="index"
      :item="item"
      v-show="item.type === 'header'"
    />
    <div class="flex relative">
      <div class="hidden xl:flex">
        <Menu
          v-for="(item, index) in menu"
          :key="index"
          :item="item"
          v-show="item.type === 'header'"
          :desktop="desktop"
        />
      </div>
      <div class="menu-mobile xl:hidden ">
       <div class="icon-menu relative">
          <img src="@/static/image/menu.svg" alt="" class="w-8 cursor-pointer transform duration-75 z-20 "  @click.prevent="abc" 
        :class="rotate"
        />
          <img src="@/static/image/close.svg" alt="" class=" ml-auto mb-10 cursor-pointer transform duration-100 ease-linear absolute top-0 w-8 " @click.prevent="xyz"
      :class="close"
      >
       </div>

      <div class=" fixed h-screen w-310 border-2 border-green-01 p-8  top-24 z-10 right-10 bg-white rounded-2xl transform duration-500 ease-linear "
      :class="icon"
      >
        <Mobile 
       v-for="(item, index) in menu"
          :key="index"
          :item="item"
          :desktop="desktop"
      />
      </div>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from "@/components/Logo";
import Menu from "@/components/Menu";
import Mobile from '@/components/Mobile'
export default {
  components: {
    Logo,
    Menu,
    Mobile
  },
  data() {
    return {
      logo: [],
      menu: [],
      mobile: true,
      desktop: true,
      mobile_menu:false

    };
  },
  async fetch() {
    this.logo = await fetch("http://localhost:3000/logo").then((res) => {
      return res.json();
    });
    this.menu = await fetch("http://localhost:3000/menu").then((res) => {
      return res.json();
    });
  },
  methods: {
    abc() {
      return this.mobile_menu = !this.mobile_menu
    },
    xyz() {
      return this.mobile_menu = !this.mobile_menu
    }
  },
  computed: {
    icon() {
      if(this.mobile_menu === true) {
        return 'opacity-1 translate-x-0 '
      } else {
        return ' opacity-0 translate-x-full'
      }
    },
    rotate() {
      if(this.mobile_menu === true) {
        return ' rotate-180 opacity-0'
      } else {
        return ' rotate-0'
      }
    },
    close() {
      if(this.mobile_menu === true) {
        return 'opacity-1  '
      } else {
        return ' opacity-0'
      }

    }
  }
};
</script>

<style scoped>
 a.nuxt-link-exact-active {
        color:#71A894;
    }
</style>