<template>
  <div id="landing-07" class="mx-auto max-w-1500">
      <Header />
      <Hero />
      <Feature />
      <Organization />
      <Investor />
      <Committed />
      <Help />
      <Open />
      <Footer />
  </div>
</template>

<script>
import Header from "@/components/Section/Header"
import Hero from '@/components/Section/Hero'
import Feature from '@/components/Section/Feature'
import Organization from '@/components/Section/organization'
import Committed from '@/components/Section/Committed'
import Investor from '@/components/Section/Investor'
import Help from '@/components/Section/Help'
import Open from '@/components/Section/Open'
import Footer from '@/components/Section/Footer'
export default {
    components: {
        Header,
        Hero,
        Feature,
        Organization,
        Committed,
        Investor,
        Help, Open,
        Footer
    }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

</style>
