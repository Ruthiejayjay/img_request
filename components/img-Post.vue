<template>
  <!-- Section 1 -->
  <section class="py-24 bg-white">
    <div class="max-w-3xl px-10 mx-auto xl:px-5">
      <div class="flex flex-col justify-center space-y-8">
        <h2
          class="
            w-full
            mx-auto
            text-4xl
            font-extrabold
            leading-none
            text-left text-gray-900
            sm:text-5xl
            md:text-7xl
          "
        >
          Upload an image
        </h2>
        <p
          class="
            w-full
            max-w-3xl
            mx-auto
            text-xl text-left text-gray-500
            md:text-2xl
          "
        >
          Get the latest trends and updates in your inbox each week. We will
          provide you with top notch designs and resources.
        </p>

        <div
          class="
            flex flex-col
            w-full
            mx-auto
            space-y-5
            md:space-y-0 md:space-x-5 md:flex-row
          "
        >
          <input
            id="url.img"
            type="file"
            class="
              flex-1
              w-full
              px-5
              py-5
              text-2xl
              bg-gray-200
              border border-gray-300
              rounded-lg
              focus:ring-4
              focus:border-blue-600
              focus:ring-blue-600
              focus:ring-opacity-50
              focus:outline-none
            "
            placeholder="Email Address"
          />
          <a
            class="
              flex-shrink-0
              px-10
              py-5
              text-2xl
              font-medium
              text-center text-white
              bg-blue-600
              rounded-lg
              focus:ring-4
              focus:ring-blue-600
              focus:ring-opacity-50
              focus:ring-offset-2
              focus:outline-none
            "
            @click.prevent="image()"
            >Post</a
          >
        </div>
        <p class="text-gray-400">
          <span class="font-medium text-gray-700">Trusted by</span> over 27,000
          subscribers.
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      url: {
        img: "",
      },
    };
  },
  methods: {
    image() {
      console.log("url: ", this.url.img);
      var axios = require("axios");
      var data = JSON.stringify({
        "url": this.url.img
    
      });

      var config = {
        method: "post",
        url: "https://jsonplaceholder.typicode.com/photos",
        headers: {
          "Content-Type": "application/json",
        },
        data: data,
      };

      axios(config)
        .then(function (response) {
          console.log(JSON.stringify(response.data));
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
};
</script>

<style>
</style>