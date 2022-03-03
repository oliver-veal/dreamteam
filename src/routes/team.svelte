<script lang="ts">
  import Menu from '$lib/menu/Menu.svelte';
  import MenuIcon from '$lib/menu/MenuIcon.svelte';

  let menuOpen = false;

  let closeMenu = () => (menuOpen = false);
</script>

<div class="w-full h-0 fixed inset-0 flex flex-col justify-between z-50">
  <div
    class="flex items-center justify-between bg-black bg-opacity-75 backdrop-blur-xl p-2.5 md:p-5"
  >
    <a href="/" sveltekit:prefetch>
      <img src="/dreamteam.svg" alt="dreamteam" width="200" />
    </a>
    <button
      on:click={() => {
        menuOpen = !menuOpen;
      }}
      class="p-2"
    >
      <MenuIcon
        bind:open={menuOpen}
        class="w-6 xl:w-8 {menuOpen &&
          '-rotate-90'} transition-transform duration-300"
        fill="#fff"
      />
    </button>
  </div>
</div>

<Menu open={menuOpen} {closeMenu} />

<div class="w-full flex space-x-8 items-start justify-center p-16 py-96">
  <h1 class="text-3xl xl:text-8xl uppercase font-light text-right">
    Who we <br /> are
  </h1>
  <h2 class="text-lg xl:text-2xl">
    We are a collection of creatives, <br /> engineers and innovators.
  </h2>
</div>

<div class="min-h-screen w-full flex flex-col">
  <div class="flex w-full flex-grow items-center justify-center">
    <p>test</p>
  </div>
  <div class="w-full flex justify-center">
    <div class="flex space-x-12 items-end">
      <div class="h-96 w-64 rounded-t-full bg-[#ff5470]" />
      <div class="h-72 w-64 rounded-t-full bg-[#ff5470]" />
      <div class="h-80 w-64 rounded-t-full bg-[#ff5470]" />
      <div class="h-64 w-64 rounded-t-full bg-[#ff5470]" />
      <div class="h-64 w-64 rounded-t-full bg-[#ff5470]" />
    </div>
  </div>
  <div class="w-full h-64 bg-[#ff5470]" />
</div>
