<script lang="ts">
  import Icon from '$lib/icon/Icon.svelte';
  import ChevronDown from '$lib/icon/heroicons/ChevronDown.js';

  import { fade, fly } from 'svelte/transition';
</script>

<section class="relative w-full h-screen flex flex-col p-5 space-y-12">
  <div class="w-full h-full absolute inset-0 flex items-center justify-center">
    <h1
      class="text-3xl lg:text-6xl uppercase font-light text-center px-8 lg:px-16"
    >
      <span in:fade={{ duration: 1000, delay: 0 }}>
        Design is more than beauty.<br />
      </span>
      <span in:fade={{ duration: 1000, delay: 1500 }}>
        Engineering is more than science.
      </span>
    </h1>
  </div>

  <div
    class="text-white absolute top-3/4 left-1/2 -translate-y-1/2 -translate-x-1/2"
    in:fly={{ y: 150, duration: 1500, delay: 3000 }}
  >
    <Icon src={ChevronDown} size="36" />
  </div>
</section>
