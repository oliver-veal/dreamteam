<script lang="ts">
  import { assets } from '$app/paths';
  import Button from '$lib/button/Button.svelte';

  import Hero from './_hero.svelte';

  let scrollY: number;
</script>

<svelte:window bind:scrollY />

<div
  class="w-full h-full p-10 fixed inset-0 flex flex-col justify-between  z-50"
>
  <div class="flex items-center justify-between">
    <img src="{assets}/dreamteam-logo.svg" alt="Dreamteam Logo" width="200" />
    <img src="{assets}/menu.svg" alt="Menu" width="30" />
  </div>
  <div class="flex items-center justify-between">
    <img src="{assets}/imperial-logo.svg" alt="Dreamteam Logo" width="200" />
    <Button>Contact</Button>
  </div>
</div>

<div class="absolute w-full h-full flex items-center justify-center">
  <Hero />
</div>

<div
  class="h-screen w-screen fixed inset-0"
  style="
    background: linear-gradient(-45deg, #c850c0, #4158d0);
    clip-path: url(#myClip);
  "
/>

<svg width="100vw" height="100vh" class="fixed inset-0">
  <defs>
    <clipPath id="myClip">
      <circle cx="50%" cy="75%" r={scrollY} />
    </clipPath>
  </defs>
</svg>
