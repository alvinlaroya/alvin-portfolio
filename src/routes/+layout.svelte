<script>
  import "aos/dist/aos.css";
  // @ts-ignore
  import AOS from "aos";

  import { onMount } from "svelte";

  import "../app.css";

  import Navbar from "../lib/components/Navbar.svelte";

  onMount(() => {
    AOS.init();
  });
</script>

<svelte:head>
  <link href="https://fonts.cdnfonts.com/css/bogart" rel="stylesheet" />
</svelte:head>

<Navbar />
<div class="p-5">
  <slot />
</div>
