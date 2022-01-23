<script lang="ts">
  import { browser } from '$app/env';
  import { fade, scale } from 'svelte/transition';
  import { OnMount } from 'fractils';

  import Button from '$lib/button/Button.svelte';
  import Icon from '$lib/icon/Icon.svelte';
  import Scroll from '$lib/scroll/scroll.svelte';

  import ImperialLogo from '$lib/logo/imperial-logo.svelte';
  import Menu from '$lib/logo/menu.svelte';
  import ChevronDown from '$lib/icon/heroicons/ChevronDown.js';

  let innerHeight: number = browser ? window.innerHeight : 0;
</script>

<svelte:window bind:innerHeight on:load={() => window.scrollTo({ top: 0 })} />

<OnMount>
  <div
    class="w-full h-full p-10 fixed inset-0 flex flex-col justify-between z-10"
    in:scale={{ duration: 1500, start: 0.9, delay: 3000 }}
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
</OnMount>

<OnMount>
  <div class="fixed w-full h-full flex items-center justify-center">
    <h1 class="text-6xl uppercase font-light text-center">
      <span in:fade={{ duration: 1000, delay: 0 }}
        >Design is more than beauty.<br /></span
      >
      <span in:fade={{ duration: 1000, delay: 1500 }}
        >Engineering is more than science.</span
      >
    </h1>
    <div in:fade={{ duration: 1500, delay: 3000 }}>
      <Icon
        src={ChevronDown}
        size="48"
        class="text-white absolute top-3/4 left-1/2 z-50 -translate-y-1/2 -translate-x-1/2"
      />
    </div>
  </div>
</OnMount>

<OnMount>
  <div in:fade={{ duration: 1500, delay: 3000 }}>
    <div
      class="h-screen w-screen fixed inset-0 z-20"
      style="
      background: linear-gradient(-45deg, #ffd3e3, #ffb4f8, #cdaaff);
      clip-path: url(#clip);
    "
    />

    <Scroll start={0} end={innerHeight} let:s>
      <svg width="100vw" height="100vh" class="fixed inset-0">
        <defs>
          <clipPath id="clip">
            <circle cx="50%" cy="75%" r="{s * 100}%" />
          </clipPath>
        </defs>
      </svg>
    </Scroll>

    <div
      class="w-full h-full p-10 fixed inset-0 flex items-center justify-center z-30 overflow-hidden text-black"
      style="clip-path: url(#clip);"
    >
      <div
        class="w-full h-full p-10 fixed inset-0 flex flex-col justify-between"
        in:scale={{ duration: 1500, start: 0.9, delay: 3000 }}
      >
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

      <h1 class="text-6xl uppercase font-light text-center">
        <span in:fade={{ duration: 1000, delay: 0 }}
          >Design is more than beauty.<br /></span
        >
        <span in:fade={{ duration: 1000, delay: 1500 }}
          >Engineering is more than science.</span
        >
      </h1>

      <Icon
        src={ChevronDown}
        size="48"
        class="text-black absolute top-3/4 left-1/2 z-50 -translate-y-1/2 -translate-x-1/2"
      />
    </div>
  </div>
</OnMount>
