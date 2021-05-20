<template>
  <div class="button ">
      <button 

      :class="button"
      >{{item.text}}</button>
  </div>
</template>

<script>
export default {
    props:{
        item:{
            type:Object
        },
        background: {
            type: String
        }
    },
    computed: {
        button() {
            if(this.background === 'early') {
                return ' px-6 py-5 bg-green-01 text-white font-bold rounded-xl border-2 border-green-01 hover:bg-pink hover:border-pink duration-300 ease-linear focus:outline-none'
            } else if( this.background === 'vote' ) {
                return 'w-full text-center padding py-3 bg-black text-white rounded-xl mt-5 duration-300 ease-linear hover:bg-green-01  font-medium focus:outline-none cursor-pointer'
            }else if( this.background === 'profile' ) {
                return 'w-full text-center padding py-3 bg-black text-white rounded-xl mt-0 duration-300 ease-linear hover:bg-green-01  font-medium focus:outline-none cursor-pointer'
            }else {
                return '  flex justify-center mt-10 font-bold padding py-5  px-6 bg-black text-white rounded-xl mt-0 duration-300 ease-linear hover:bg-green-01  font-medium focus:outline-none cursor-pointer mx-auto'
            }
        }
    }

}
</script>

<style>

</style>