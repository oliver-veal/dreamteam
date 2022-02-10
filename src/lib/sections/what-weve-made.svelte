<script lang="ts">
  import Mask from '$lib/projects/mask.svelte';
  import { slide } from 'svelte/transition';
  import X from '$lib/icon/heroicons/X.js';
  import Icon from '$lib/icon/Icon.svelte';

  let maskOpen = false;
</script>

<section
  class="relative w-full flex flex-col space-y-24 xl:space-y-48 left-0"
  id="what-weve-made"
>
  <div class="w-full text-center">
    <h1 class="text-3xl xl:text-6xl uppercase font-light">What we've made</h1>
    <p class="xl:text-2xl">A small glimpse at our work</p>
  </div>

  <div
    class="{maskOpen &&
      '-translate-x-[100vw]'} transition-transform duration-300 w-[200vw] flex justify-center"
  >
    <div transition:slide class="flex w-[100vw] justify-center items-start">
      <div
        class="flex flex-col sm:flex-row space-y-12 sm:space-y-0 w-full max-w-[800px] space-x-5 px-5 justify-between"
      >
        <button
          class="relative group cursor-pointer"
          on:click={() => (maskOpen = true)}
        >
          <img
            src="/what-weve-made/mask.png"
            alt="Face Mask Project"
            class="max-h-[325px] object-cover group-hover:-translate-y-8 transition-transform duration-300"
          />
          <div class="absolute bottom-0 left-0 flex flex-col space-y-2.5 z-10">
            <img src="/wwd/mask.svg" class="w-10 h-10" alt="Mask" />
            <p class="font-bold text-lg">Imperial Face Mask</p>
          </div>
        </button>

        <div class="relative group cursor-pointer flex items-center">
          <img
            src="/what-weve-made/bic.png"
            alt="Blast Injury Conference Project"
            class="max-h-[325px] object-cover group-hover:-translate-y-8 transition-transform duration-300"
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
            class="max-h-[325px] object-cover group-hover:-translate-y-8 transition-transform duration-300"
          />
          <div class="absolute bottom-0 left-0 flex flex-col space-y-2.5 z-10">
            <img src="/wwd/bmx.svg" class="w-10 h-10" alt="BMX" />
            <p class="font-bold text-lg">BMX Project</p>
          </div>
        </div>
      </div>
    </div>

    <div class="flex flex-col w-[100vw]">
      <div class="w-full static flex items-center justify-end z-40">
        <button on:click={() => (maskOpen = false)} class="p-2.5 md:p-5">
          <Icon src={X} class="w-12 xl:w-14" />
        </button>
      </div>
      {#if maskOpen}
        <Mask />
      {/if}
    </div>
  </div>
</section>
