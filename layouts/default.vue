<template>
    <div v-if="alphineready">
       <navigation />
       <Nuxt />
       <img-footer />
    
  </div>
</template>

<script>
import ImgFooter from '~/components/img-Footer.vue'
import Navigation from '~/components/Navigation.vue'
export default {
  components: { Navigation, ImgFooter },
   data() {
    return {
      alphineready: false,
    };
  },

  head() {
    return {
      title: "IMG-REQUEST", // Other meta information
      script: [
        {
          hid: "alphine",
          src: "https://cdnjs.cloudflare.com/ajax/libs/alpinejs/2.8.0/alpine.js",
          // Changed after script load
          callback: () => {
            this.alphineready = true;
          },
        },
      ],
    };
  },

}
</script>

<style>

</style>