<template>
  <div class="help-center mb-20 max-w-1500 mx-auto">
    <Heading
      v-for="(head, index) in heading"
      :key="index"
      :head="head"
      v-show="head.type === 'help'"
      :section="head.type"
    />
    <Heading
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
      :item="item"
    />
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
      :item="item"
    />
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
      :item="item"
    />
    <Button
      v-for="(item, index) in button"
      :key="index"
      v-show="item.type === 'more'"
      :item="item"
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