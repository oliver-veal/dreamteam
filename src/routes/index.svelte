<script lang="ts">
  import { slide, fly, scale, fade } from 'svelte/transition';

  import { scrollto } from 'svelte-scrollto';

  import * as animateScroll from 'svelte-scrollto';

  animateScroll.setGlobalOptions({
    offset: -200,
  });

  import Menu from '$lib/logo/menu.svelte';
  import Hero from '$lib/sections/hero.svelte';
  import WhatWeveMade from '$lib/sections/what-weve-made.svelte';
  import HowWeDoIt from '$lib/sections/how-we-do-it.svelte';
  import WhatTheySay from '$lib/sections/what-they-say.svelte';
  import WhatsNext from '$lib/sections/whats-next.svelte';
  import WhatWeDo from '$lib/sections/what-we-do.svelte';
  import WhoWeAre from '$lib/sections/who-we-are.svelte';
  import Mask from '$lib/projects/mask.svelte';
  import { OnMount } from 'fractils';

  import Icon from '$lib/icon/Icon.svelte';
  import ChevronDown from '$lib/icon/heroicons/ChevronDown.js';
  import Button from '$lib/button/Button.svelte';
  import { Parallax, ParallaxLayer } from '$lib/svelte-parallax/index';

  let menuOpen = false;
  let maskOpen = false;
</script>

<head>
  <title> Dreamteam </title>
</head>

<div class="w-full h-0 fixed inset-0 flex flex-col justify-between z-40">
  <div
    class="flex items-center justify-between bg-black bg-opacity-75 backdrop-blur-lg p-2.5 md:p-5"
  >
    <h1 class="text-3xl xl:text-5xl select-none">
      dream<span class="font-light">team</span>
    </h1>
    <button on:click={() => (menuOpen = !menuOpen)} class="p-2">
      <Menu
        bind:open={menuOpen}
        class="w-6 xl:w-8 {menuOpen &&
          '-rotate-90'} transition-transform duration-300"
        fill="#fff"
      />
    </button>
  </div>
</div>

{#if menuOpen}
  <div
    transition:slide
    class="w-screen h-screen fixed inset-0 overflow-y-auto bg-black z-30 flex flex-col items-center justify-center space-y-12"
  >
    <button use:scrollto={'#who-we-are'} on:click={() => (menuOpen = false)}>
      <h1 class="text-3xl uppercase font-light group-hover:pl-12">
        Who we are
      </h1>
    </button>

    <button use:scrollto={'#what-we-do'} on:click={() => (menuOpen = false)}>
      <h1 class="text-3xl uppercase font-light group-hover:pl-12">
        What we do
      </h1>
    </button>

    <button
      use:scrollto={'#what-weve-made'}
      on:click={() => (menuOpen = false)}
    >
      <h1 class="text-3xl uppercase font-light group-hover:pl-12">
        What we've made
      </h1>
    </button>

    <button use:scrollto={'#how-we-do-it'} on:click={() => (menuOpen = false)}>
      <h1 class="text-3xl uppercase font-light group-hover:pl-12">
        How we do it
      </h1>
    </button>

    <button use:scrollto={'#what-they-say'} on:click={() => (menuOpen = false)}>
      <h1 class="text-3xl uppercase font-light group-hover:pl-12">
        What they say
      </h1>
    </button>

    <button use:scrollto={'#whats-next'} on:click={() => (menuOpen = false)}>
      <h1 class="text-3xl uppercase font-light group-hover:pl-12">
        What's next
      </h1>
    </button>
  </div>
{/if}

{#if maskOpen}
  <div
    transition:scale
    class="w-screen h-screen fixed inset-0 overflow-y-auto bg-black z-50"
  >
    <Mask bind:open={maskOpen} />
  </div>
{/if}

<main class="space-y-48 xl:space-y-96">
  <Parallax sections={2} threshold={{ top: 0, bottom: 0 }}>
    <ParallaxLayer rate={0.2}>
      <div class="flex w-full h-full items-center justify-center">
        <OnMount>
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
        </OnMount>
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.4}>
      <div class="flex w-full h-full items-center justify-center">
        <OnMount>
          <div
            class="text-white absolute top-3/4 left-1/2 -translate-y-1/2 -translate-x-1/2"
            in:fly={{ y: 150, duration: 1500, delay: 3000 }}
          >
            <Icon src={ChevronDown} size="36" />
          </div>
        </OnMount>
      </div>
    </ParallaxLayer>
    <ParallaxLayer offset={1} rate={0.2} style="z-index: 100;">
      <div
        id="who-we-are"
        class="flex flex-col w-full h-full items-center justify-center z-50"
      >
        <h1
          class="text-5xl uppercase font-light text-center flex flex-col px-32 select-none"
        >
          We are dream team
        </h1>
        <a href="mailto:contact@dreamteamdesign.co.uk" class="mt-12">
          <Button>Contact</Button>
        </a>
      </div>
    </ParallaxLayer>
    <ParallaxLayer offset={1} rate={0.15}>
      <div class="flex items-center justify-center">
        <div
          class="rounded-full w-10 xl:w-14 h-10 xl:h-14 absolute left-[75%] top-[37%]"
          style="background: url(/faces/1.png); background-size: cover;"
        />
      </div>
    </ParallaxLayer>
    <ParallaxLayer offset={1} rate={0.175}>
      <div class="flex items-center justify-center">
        <div
          class="rounded-full w-16 xl:w-20 h-16 xl:h-20 absolute left-[65%] top-[28%]"
          style="background: url(/faces/2.png); background-size: cover;"
        />
      </div>
    </ParallaxLayer>

    <ParallaxLayer offset={1} rate={0.225}>
      <div class="flex items-center justify-center">
        <div
          class="rounded-full w-24 xl:w-28 h-24 xl:h-28 absolute left-[17.5%] top-[67%]"
          style="background: url(/faces/3.png); background-size: cover;"
        />
      </div></ParallaxLayer
    >
    <ParallaxLayer offset={1} rate={0.25}>
      <div class="flex items-center justify-center">
        <div
          class="rounded-full w-28 xl:w-36 h-28 xl:h-36 absolute left-[60%] top-[75%]"
          style="background: url(/faces/4.png); background-size: cover;"
        />
      </div>
    </ParallaxLayer>
    <ParallaxLayer offset={1} rate={0.275}>
      <div class="flex items-center justify-center">
        <div
          class="rounded-full w-32 xl:w-48 h-32 xl:h-48 absolute left-[20%] top-[16%]"
          style="background: url(/faces/5.png); background-size: cover;"
        />
      </div>
    </ParallaxLayer>
  </Parallax>

  <!-- <WhoWeAre /> -->

  <WhatWeDo />

  <WhatWeveMade />

  <HowWeDoIt />

  <WhatTheySay />

  <WhatsNext />
</main>

<footer
  class="px-12 p-24 xl:p-48 flex flex-col sm:flex-row space-y-12 sm:space-y-0 justify-between items-center z-50"
  style="background: linear-gradient(-20deg, rgb(5,255,241) 25%, rgb(255,84,112) 75%);"
>
  <div class="flex flex-col sm:space-y-2">
    <b class="uppercase font-bold">Contact</b>
    <p>DreamTeam London</p>
    <p>South Kensington</p>
    <p>04 56784900</p>
  </div>
  <p>All Rights Reserved</p>
</footer>
