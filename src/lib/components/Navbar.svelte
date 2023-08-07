<script>
  import {
    Navbar,
    NavBrand,
    NavLi,
    NavUl,
    NavHamburger,
  } from "flowbite-svelte";
</script>

<Navbar let:hidden let:toggle class="z-50">
  <NavBrand href="/">
    <span
      class="self-center whitespace-nowrap text-xl font-normal dark:text-white"
    >
      Alvin
    </span>
  </NavBrand>
  <NavHamburger on:click={toggle} />
  <NavUl {hidden}>
    <NavLi class="font-light" href="/" active={true}>Home</NavLi>
    <NavLi class="font-light" href="/about">About</NavLi>
    <NavLi class="font-light" href="/skills">Skills</NavLi>
    <NavLi class="font-light" href="/services">Services</NavLi>
    <NavLi class="font-light" href="/portfolio">Portfolio</NavLi>
    <NavLi class="font-light" href="/contact">Contact</NavLi>
  </NavUl>
</Navbar>
