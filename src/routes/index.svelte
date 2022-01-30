<script lang="ts">
  import { browser } from '$app/env';
  import { fade, scale, fly } from 'svelte/transition';
  import { OnMount } from 'fractils';

  import Button from '$lib/button/Button.svelte';
  import Icon from '$lib/icon/Icon.svelte';
  import Scroll from '$lib/scroll/scroll.svelte';

  import ImperialLogo from '$lib/logo/imperial-logo.svelte';
  import Menu from '$lib/logo/menu.svelte';
  import ChevronDown from '$lib/icon/heroicons/ChevronDown.js';

  let innerHeight: number = browser ? window.innerHeight : 0;
  let scrollY;
</script>

<svelte:window
  bind:innerHeight
  bind:scrollY
  on:load={() => window.scrollTo({ top: 0 })}
/>

<OnMount>
  <div
    class="w-full h-full p-10 fixed inset-0 flex flex-col justify-between z-20"
    in:scale={{ duration: 500, start: 0.9, delay: 3000 }}
  >
    <div class="flex items-center justify-between">
      <h1 class="text-5xl">
        dream<span class="font-light">team</span>
      </h1>
      <Menu width="30" fill="#fff" />
    </div>
    <div class="flex items-center justify-between">
      <ImperialLogo width="200" fill="#fff" />

      <Button>Contact</Button>
    </div>
  </div>
</OnMount>

<OnMount>
  <div
    class="fixed w-full h-full flex flex-col items-center justify-center z-30"
  >
    <Scroll start={innerHeight * 0.75} end={innerHeight * 1} let:s={out}>
      <h1
        class="absolute text-6xl uppercase font-light text-center flex flex-col"
        style="opacity: {1 - out}"
      >
        <span in:fade={{ duration: 1000, delay: 0 }}>
          Design is more than beauty.
        </span>
        <span in:fade={{ duration: 1000, delay: 1500 }}>
          Engineering is more than science.
        </span>
      </h1>
    </Scroll>

    <Scroll start={innerHeight * 1} end={innerHeight * 1.1} let:s>
      <Scroll start={innerHeight * 1.9} end={innerHeight * 2} let:s={out}>
        <h1
          class="absolute text-6xl uppercase font-light text-center flex flex-col"
          style="opacity: {s - out}"
        >
          <span>We know what shapes the future.</span>
          <span>We know design engineering can change the world.</span>
        </h1>
      </Scroll>
    </Scroll>

    <Scroll start={innerHeight * 2} end={innerHeight * 2.1} let:s>
      <Scroll start={innerHeight * 2.9} end={innerHeight * 3} let:s={out}>
        <h1
          class="absolute text-6xl uppercase font-light text-center flex flex-col"
          style="opacity: {s - out}"
        >
          <span
            >We are tomorrow's designers, engineers, makers and thinkers.</span
          >
          <span>We think freely, paving new ways of thinking and doing.</span>
        </h1>
      </Scroll>
    </Scroll>

    <div
      in:fly={{ y: 100, duration: 1500, delay: 3000 }}
      class="text-white absolute top-3/4 left-1/2 z-50 -translate-y-1/2 -translate-x-1/2"
    >
      <Icon src={ChevronDown} size="48" />
    </div>
  </div>
</OnMount>

<OnMount>
  <div in:fade={{ duration: 500, delay: 0 }}>
    <div
      class="h-screen w-screen fixed inset-0"
      style="
          background: linear-gradient(-45deg, rgba(255,188,85,1) 0%, rgba(223,0,56,1) 50%, rgba(158,65,208,1) 100%;
          background-position: 0.25;
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
  </div>
</OnMount>
