<script>
  import Social from "./Social.svelte";
  import Description from "./Description.svelte";

  import Mouse from "../icons/Mouse.svelte";
  import ArrowDown from "../icons/ArrowDown.svelte";
</script>

<div class="flex justify-center sm:my-28 -mt-12">
  <div
    class="h-screen md:h-[300px] lg:h-[500px] grid content-center md:flex md:gap-24"
  >
    <div
      class="flex justify-center md:mt-0 order-1 md:order-3 text-center"
      data-aos="zoom-in"
    >
      <img src="/alvin.png" alt="" class="w-[70%] md:w-[400px] lg:w-[500px]" />
    </div>
    <div
      class="md:grid content-center order-2 md:order-2 my-8 text-center md:text-left"
    >
      <Description class="h-96" />
    </div>
    <div class="flex justify-center md:grid content-center order-3 md:order-1">
      <Social class="h-60" />
    </div>
    <div
      class="animate-bounce order-last flex md:hidden mt-20 justify-center"
      data-aos="fade-up"
    >
      <Mouse />
      <p class="text-sm font-thin mx-2">Scroll down</p>
      <ArrowDown />
    </div>
  </div>
</div>
