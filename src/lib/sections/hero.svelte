<script lang="ts">
  import Icon from '$lib/icon/Icon.svelte';
  import ChevronDown from '$lib/icon/heroicons/ChevronDown.js';
  import { OnMount } from 'fractils';

  import { fade, fly } from 'svelte/transition';
  import Button from '$lib/button/Button.svelte';
</script>

<OnMount>
  <section class="relative w-full h-screen flex flex-col space-y-12">
    <div
      class="w-full h-full absolute inset-0 flex items-center justify-center"
    >
      <h1
        class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16"
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
      class="text-white absolute top-[66%] left-1/2 -translate-y-1/2 -translate-x-1/2"
      in:fly={{ y: 150, duration: 1500, delay: 3000 }}
    >
      <Icon src={ChevronDown} size="36" />
    </div>

    <div class="absolute bottom-0 left-0 w-full py-5">
      <div class="flex items-end justify-between px-8 xl:px-16">
        <img
          src="/imperial-logo.png"
          class="w-[200px]"
          alt="Imperial College London Consultants"
        />

        <div class="pointer-events-auto">
          <a href="mailto:contact@dreamteamdesign.co.uk">
            <Button>Contact</Button>
          </a>
        </div>
      </div>
    </div>
  </section>
</OnMount>
