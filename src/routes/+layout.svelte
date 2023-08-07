<script>
  import "../app.css";

  import Navbar from "../lib/components/Navbar.svelte";
</script>

<svelte:head>
  <link href="https://fonts.cdnfonts.com/css/bogart" rel="stylesheet" />
</svelte:head>

<Navbar />
<div class="p-5">
  <slot />
</div>
