<script lang="ts">
  import Button from '$lib/button/Button.svelte';

  import ImperialLogo from '$lib/logo/imperial-logo.svelte';
  import Menu from '$lib/logo/menu.svelte';

  let scrollY: number;
  let innerHeight: number;

  $: console.log(scrollY / innerHeight);
</script>

<svelte:window bind:scrollY bind:innerHeight />

<div
  class="w-full h-full p-10 fixed inset-0 flex flex-col justify-between z-10"
>
  <div class="flex items-center justify-between">
    <h1 class="text-5xl">dreamteam</h1>
    <Menu width="30" fill="#fff" />
  </div>
  <div class="flex items-center justify-between">
    <ImperialLogo width="200" fill="#fff" />

    <Button>Contact</Button>
  </div>
</div>

<div class="fixed w-full h-full flex items-center justify-center">
  <h1 class="text-6xl uppercase font-light">
    Design is more than beauty.<br />
    Engineering is more than science.
  </h1>
</div>

<div
  class="h-screen w-screen fixed inset-0 z-20"
  style="
    background: linear-gradient(-45deg, #ffd3e3, #ffb4f8, #cdaaff);
    clip-path: url(#myClip);
  "
/>

<svg width="100vw" height="100vh" class="fixed inset-0">
  <defs>
    <clipPath id="myClip">
      <circle cx="50%" cy="50%" r="{(scrollY * 100) / innerHeight}%" />
    </clipPath>
  </defs>
</svg>

<div
  class="w-full h-full p-10 fixed inset-0 flex items-center justify-center z-30 overflow-hidden text-black"
  style="clip-path: url(#myClip);"
>
  <div class="w-full h-full p-10 fixed inset-0 flex flex-col justify-between">
    <div class="flex items-center justify-between">
      <h1 class="text-5xl">dreamteam</h1>
      <Menu width="30" fill="#000" />
    </div>
    <div class="flex items-center justify-between">
      <ImperialLogo width="200" fill="#000" />
      <button on:click class="py-2 px-8 ring-2 ring-black rounded-full">
        <span class="uppercase"> Contact </span>
      </button>
    </div>
  </div>

  <h1 class="text-6xl uppercase font-light">
    Design is more than beauty.<br />
    Engineering is more than science.
  </h1>
</div>
