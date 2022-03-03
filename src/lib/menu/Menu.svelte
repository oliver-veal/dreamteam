<script lang="ts">
  import { slide } from 'svelte/transition';

  export let closeMenu: () => any;
  export let open: boolean;
</script>

<svelte:window
  on:keydown={(e) => {
    if (e.key === 'Escape') closeMenu();
  }}
/>

{#if open}
  <div
    transition:slide
    class="w-screen h-screen fixed inset-0 overflow-y-auto bg-black bg-opacity-75 backdrop-blur-xl flex flex-col items-center justify-center z-40"
  >
    <a href="/" on:click={closeMenu} sveltekit:prefetch class="p-5">
      <h1 class="text-3xl uppercase font-light select-none">Home</h1>
    </a>

    <a href="/projects" on:click={closeMenu} sveltekit:prefetch class="p-5">
      <h1 class="text-3xl uppercase font-light select-none">Projects</h1>
    </a>

    <a href="/team" on:click={closeMenu} sveltekit:prefetch class="p-5">
      <h1 class="text-3xl uppercase font-light select-none">Team</h1>
    </a>

    <a href="mailto:contact@dreamteamdesign.co.uk" class="btn mt-5">
      <h1 class="uppercase text-xs xl:text-base">Contact</h1>
    </a>
  </div>
{/if}
