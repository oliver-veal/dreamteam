<script lang="ts">
  import { slide, fade } from 'svelte/transition';
  import Mask from '$lib/projects/mask.svelte';
  import Icon from '$lib/icon/Icon.svelte';
  import X from '$lib/icon/heroicons/X.js';

  let maskOpen = true;
</script>

<section
  class="w-full flex flex-col p-10 space-y-24 xl:space-y-48 items-center"
  id="what-weve-made"
>
  <div class="w-full text-center">
    <h1 class="text-3xl xl:text-6xl uppercase font-light">What we've made</h1>
    <p class="xl:text-2xl">A small glimpse at our work</p>
  </div>

  <div
    class="flex flex-col sm:flex-row space-y-12 sm:space-y-0 w-full items-center justify-between space-x-5 max-w-[800px]"
  >
    <button
      class="relative group cursor-pointer"
      on:click={() => (maskOpen = true)}
    >
      <img
        src="/what-weve-made/mask.png"
        alt="Face Mask Project"
        class="w-full max-h-[325px] object-cover group-hover:-translate-y-8 transition-transform duration-300"
      />
      <div class="absolute bottom-0 left-0 flex flex-col space-y-2.5 z-10">
        <img src="/wwd/mask.svg" class="w-10 h-10" alt="Mask" />
        <p class="font-bold text-lg">Imperial Face Mask</p>
      </div>
    </button>
    <div class="relative group cursor-pointer">
      <img
        src="/what-weve-made/bic.png"
        alt="Blast Injury Conference Project"
        class="w-full max-h-[325px] object-cover group-hover:-translate-y-8 transition-transform duration-300"
      />
      <div class="absolute bottom-0 left-0 flex flex-col space-y-2.5 z-10">
        <img src="/wwd/bic.svg" class="w-10 h-10" alt="BIC" />
        <p class="font-bold text-lg">Blast Injury Conference</p>
      </div>
    </div>
    <div class="relative group cursor-pointer">
      <img
        src="/what-weve-made/bmx.png"
        alt="BMX Project"
        class="w-full max-h-[325px] object-cover group-hover:-translate-y-8 transition-transform duration-300 select-none"
      />
      <div class="absolute bottom-0 left-0 flex flex-col space-y-2.5 z-10">
        <img src="/wwd/bmx.svg" class="w-10 h-10" alt="BMX" />
        <p class="font-bold text-lg">BMX Project</p>
      </div>
    </div>
  </div>
</section>

{#if maskOpen}
  <div transition:slide class="fixed inset-0 w-screen h-screen bg-black z-20">
    <div
      class="h-screen  overflow-y-auto flex flex-col justify-center items-center"
    >
      <button on:click={() => (maskOpen = false)} class="p-2.5 md:p-5">
        <Icon src={X} class="w-12 xl:w-14" />
      </button>
      <!-- <div transition:fade> -->
      <Mask />
      <!-- </div> --->
    </div>
  </div>
{/if}
