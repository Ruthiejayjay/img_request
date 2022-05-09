<template>
  <div>
    <section class="text-gray-400 bg-gray-900 body-font">
      <div class="container px-5 py-24 mx-auto">
        <div class="flex flex-col">
          <div class="h-1 bg-gray-800 rounded overflow-hidden">
            <div class="w-24 h-full bg-indigo-500"></div>
          </div>
          <div class="flex flex-wrap sm:flex-row flex-col py-6 mb-12">
            <h1
              class="
                sm:w-2/5
                text-white
                font-medium
                title-font
                text-2xl
                mb-2
                sm:mb-0
              "
            >
              Space The Final Frontier
            </h1>
            <p class="sm:w-3/5 leading-relaxed text-base sm:pl-10 pl-0">
              Street art subway tile salvia four dollar toast bitters selfies
              quinoa yuccie synth meditation iPhone intelligentsia prism tofu.
              Viral gochujang bitters dreamcatcher.
            </p>
          </div>
        </div>
        <div class="flex flex-wrap sm:-m-4 -mx-4 -mb-10 -mt-4">
          <!-- <div class="p-4 md:w-1/3 sm:mb-0 mb-6">
            <div class="rounded-lg h-64 overflow-hidden">
              <img
                alt="content"
                class="object-cover object-center h-full w-full"
                :src="fimg"
              />
            </div>
            <h2 class="text-xl font-medium title-font text-white mt-5">
              Shooting Stars
            </h2>
            <p class="text-base leading-relaxed mt-2">
              Swag shoindxgoitch literally meditation subway tile tumblr
              cold-pressed. Gastropub street art beard dreamcatcher neutra,
              ethical XOXO lumbersexual.
            </p>
            <a class="text-indigo-400 inline-flex items-center mt-3"
              >Learn More
              <svg
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                class="w-4 h-4 ml-2"
                viewBox="0 0 24 24"
              >
                <path d="M5 12h14M12 5l7 7-7 7"></path>
              </svg>
            </a>
          </div>
          <div class="p-4 md:w-1/3 sm:mb-0 mb-6">
            <div class="rounded-lg h-64 overflow-hidden">
              <img
                alt="content"
                class="object-cover object-center h-full w-full"
                :src="fimg"
              />
            </div>
            <h2 class="text-xl font-medium title-font text-white mt-5">
              The Catalyzer
            </h2>
            <p class="text-base leading-relaxed mt-2">
              Swag shoindxigoitch literally meditation subway tile tumblr
              cold-pressed. Gastropub street art beard dreamcatcher neutra,
              ethical XOXO lumbersexual.
            </p>
            <a class="text-indigo-400 inline-flex items-center mt-3"
              >Learn More
              <svg
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                class="w-4 h-4 ml-2"
                viewBox="0 0 24 24"
              >
                <path d="M5 12h14M12 5l7 7-7 7"></path>
              </svg>
            </a>
          </div> -->
          <div class="p-4 md:w-1/3 sm:mb-0 mb-6">
            <div v-for="item in image" :key="item.id" class="rounded-lg h-64 overflow-hidden">
              <img
                alt="content"
                class="object-cover object-center h-full w-full"
                :src="item"
              />
            </div>
            <h2 class="text-xl font-medium title-font text-white mt-5">
              The 400 Blows
            </h2>
            <p class="text-base leading-relaxed mt-2">
              Swag shoindegoitch literally meditation subway tile tumblr
              cold-pressed. Gastropub street art beard dreamcatcher neutra,
              ethical XOXO lumbersexual.
            </p>
            <a class="text-indigo-400 inline-flex items-center mt-3"
              >Learn More
              <svg
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                class="w-4 h-4 ml-2"
                viewBox="0 0 24 24"
              >
                <path d="M5 12h14M12 5l7 7-7 7"></path>
              </svg>
            </a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
    image: []
    };
  },
  methods:{
   populateImageBasket(item, index){
     
     console.log('image retrieved: ', item.url);
     this.image.push(item.url);
      
      //loop to get only three images
     // for (let image = 0; image < 3; image++)


    // console.log('imageArr: ', this.image);

   }
  },
  mounted() {
    var axios = require("axios");

    Array.from({length: 5}, (v, i) => i).forEach((index) => {
      var config = {
        method: "get",
        url: `https://jsonplaceholder.typicode.com/photos/${index + 1}`,
        headers: {},
      };
  
      axios(config)
        .then( (response) => {
           const image = response.data
           this.image.push(image.url);
          //console.log(images);
          // for(const image of images) {
          //     this.fimg = image.url
          // }
  
          // images.forEach(this.populateImageBasket );
          
          // images.forEach(images => {
          //     this.fimg = images.url
          // });
          //this.fimg = response.data[0, 2].url
          // this.fimg = response.data.url
        })
        .catch(function (error) {
  
          console.log(error);
        });
    });
  },
};
</script>

<style>
</style>