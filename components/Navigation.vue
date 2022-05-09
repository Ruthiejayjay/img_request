<template>
  <div class="bg-white">
    <nav
      x-data="{ mobile: false }"
      class="
        relative
        z-40
        py-4
        pt-5
        mx-auto
        md:pb-6
        max-w-7xl
        md:flex md:justify-between md:items-center
        w-full
      "
    >
      <div class="relative pt-1 z-20 flex items-end justify-between">
        <!-- Mobile menu button -->
        <div x-on:click="mobile = !mobile" class="flex md:hidden">
          <button
            type="button"
            class="
              text-gray-600
              hover:text-gray-600
              focus:outline-none focus:text-gray-600
            "
            aria-label="toggle menu"
          >
            <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
              <path
                fill-rule="evenodd"
                d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
              ></path>
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
      <div
        x-bind:class="{ hidden: !mobile, flex: mobile }"
        class="
          left-0
          z-10
          px-6
          items-center
          justify-center
          w-full
          font-semibold
          select-none
          md:flex
          lg:absolute
        "
      >
        <div
          class="
            flex flex-col
            justify-end
            w-full
            mt-4
            pl-7
            space-y-2
            md:mt-0 md:flex-row md:space-x-6
            lg:space-x-8
            xl:space-x-10
            md:space-y-0
          "
        >
          <NuxtLink
            to="/"
            class="
              relative
              inline-block
              text-base text-black
              font-bold
              transition
              duration-150
              ease
              hover:text-green-300
            "
          >
            <span class="block">Home</span>
          </NuxtLink>

          <NuxtLink
            to="/about"
            class="
              relative
              inline-block
              text-base text-black
              font-bold
              transition
              duration-150
              ease
              hover:text-green-300
            "
          >
            <span class="block">About Us</span>
          </NuxtLink>
          <NuxtLink
            to="/what-we-do"
            class="
              relative
              inline-block
              text-base text-black
              font-bold
              transition
              duration-150
              ease
              hover:text-green-300
            "
          >
            <span class="block">What We Do</span>
          </NuxtLink>

          <a
            href="#_"
            class="
              relative
              inline-block
              text-base text-black
              font-bold
              transition
              duration-150
              ease
              hover:text-green-300
            "
          >
            <span class="block">Blog</span>
          </a>

          <NuxtLink to="/contact"
            class="
              relative
              inline-block
              text-base text-black
              font-bold
              transition
              duration-150
              ease
              hover:text-green-300
            "
          >
            <span class="block">Contact Us</span>
          </NuxtLink>
          <a
            href="https://pay-project1.netlify.app/signin/"
            class="
              px-3
              py-1
              w-20
              text-center
              relative
              inline-block
              text-base text-black
              font-bold
              bg-white
              border border-green-200
              bg-green-400
              rounded
              transition
              duration-150
              ease
              hover:text-white hover:bg-green-600
            "
          >
            <span class="block">Login</span>
          </a>
        </div>
      </div>

      <div
        x-bind:class="{ flex: mobile, 'hidden md:flex': !mobile }"
        class="
          relative
          z-20
          flex-col
          justify-center
          pr-5
          mt-4
          space-y-8
          md:pr-3
          lg:pr-0
          md:flex-row md:space-y-0 md:items-center md:space-x-6 md:mt-0
        "
      ></div>
    </nav>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>