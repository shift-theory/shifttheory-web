<template lang="html">
  <div
    class="main bg-gray-100 min-h-screen flex flex-col md:flex-row justify-center items-center text-center mx-auto"
  >
    <!-- --------------------------------------------- -->
    <!-- ShiftTheory -->
    <nuxt-link to="/ecc" class="m-0 md:mx-6 lg:mx-8">
      <app-logotype class="flex w-80 md:w-96 lg:w-112" />
      <app-logomark class="w-8" />
      <h2
        class="absolute bottom-0 uppercase text-xs font-bold tracking tracking-widest left-0 right-0 mb-4 text-brand-500"
      >
        Tools For The awakened<br />
        <span class="text-brand-400 font-normal">Choose Your Path</span>
      </h2>
    </nuxt-link>
  </div>
</template>

<script>
import AppLogotype from '~/components/AppLogotype'
import AppLogomark from '~/components/AppLogomark'

export default {
  components: {
    AppLogotype,
    AppLogomark
  }
}
</script>

<style lang="postcss"></style>
