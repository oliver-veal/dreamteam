<script lang="ts">
  import { slide, fly, scale, fade } from 'svelte/transition';

  import { scrollto } from 'svelte-scrollto';

  import * as animateScroll from 'svelte-scrollto';

  animateScroll.setGlobalOptions({
    offset: -50,
  });
  import X from '$lib/icon/heroicons/X.js';

  import Menu from '$lib/logo/menu.svelte';
  import WhatWeveMade from '$lib/sections/what-weve-made.svelte';
  import HowWeDoIt from '$lib/sections/how-we-do-it.svelte';
  import WhatTheySay from '$lib/sections/what-they-say.svelte';
  import WhatsNext from '$lib/sections/whats-next.svelte';
  import WhatWeDo from '$lib/sections/what-we-do.svelte';
  import Mask from '$lib/projects/mask.svelte';
  import { OnMount } from 'fractils';

  import Icon from '$lib/icon/Icon.svelte';
  import ChevronDown from '$lib/icon/heroicons/ChevronDown.js';
  import Button from '$lib/button/Button.svelte';
  import { Parallax, ParallaxLayer } from '$lib/svelte-parallax/index';
  import Bmx from '$lib/projects/bmx.svelte';

  let panelOpen = false;
  let panelContent = 'menu';

  let closeMenu = () => (panelOpen = false);
</script>

<head>
  <title> Dreamteam </title>
</head>

<div class="w-full h-0 fixed inset-0 flex flex-col justify-between z-50">
  <div
    class="flex items-center justify-between bg-black bg-opacity-75 backdrop-blur-xl p-2.5 md:p-5"
  >
    <!-- <h1 class="text-3xl xl:text-5xl select-none"> -->
    <!-- dream<span class="font-light">team</span> -->
    <!-- </h1> -->

    <img src="/dreamteam.svg" alt="dreamteam" width="200" />

    <button
      on:click={() => {
        panelOpen = !panelOpen;
        panelContent = 'menu';
      }}
      class="p-2"
    >
      <Menu
        bind:open={panelOpen}
        class="w-6 xl:w-8 {panelOpen &&
          '-rotate-90'} transition-transform duration-300"
        fill="#fff"
      />
    </button>
  </div>
</div>

{#if panelOpen && panelContent === 'mask'}
  <div
    transition:fade
    class="fixed inset-0 w-screen h-screen bg-black bg-opacity-75 backdrop-blur-xl z-20 overflow-y-auto"
  >
    <div class="min-h-screen flex flex-col justify-center items-center pt-16">
      <div transition:fade>
        <Mask />
      </div>
    </div>
  </div>
{/if}

{#if panelOpen && panelContent === 'bmx'}
  <div
    transition:fade
    class="fixed inset-0 w-screen h-screen bg-black bg-opacity-75 backdrop-blur-xl z-20 overflow-y-auto"
  >
    <div class="min-h-screen flex flex-col justify-center items-center pt-16">
      <div transition:fade>
        <Bmx />
      </div>
    </div>
  </div>
{/if}

{#if panelOpen && panelContent === 'menu'}
  <div
    transition:slide
    class="w-screen h-screen fixed inset-0 overflow-y-auto bg-black bg-opacity-75 backdrop-blur-xl flex flex-col items-center justify-center z-40"
  >
    <button on:click={closeMenu} use:scrollto={'#what-we-do'} class="p-5">
      <h1 class="text-3xl uppercase font-light select-none">What we do</h1>
    </button>

    <button use:scrollto={'#what-weve-made'} on:click={closeMenu} class="p-5">
      <h1 class="text-3xl uppercase font-light select-none">What we've made</h1>
    </button>

    <button use:scrollto={'#how-we-do-it'} on:click={closeMenu} class="p-5">
      <h1 class="text-3xl uppercase font-light select-none">How we do it</h1>
    </button>

    <button use:scrollto={'#what-they-say'} on:click={closeMenu} class="p-5">
      <h1 class="text-3xl uppercase font-light select-none">What they say</h1>
    </button>

    <button use:scrollto={'#whats-next'} on:click={closeMenu} class="p-5">
      <h1 class="text-3xl uppercase font-light select-none">What's next</h1>
    </button>
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
    <ParallaxLayer offset={1} rate={0.2} style="z-index: 60;">
      <div class="flex flex-col w-full h-full items-center justify-center z-30">
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
        on:click={() => {
          panelContent = 'mask';
          panelOpen = true;
        }}
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
      <button
        class="relative group cursor-pointer"
        on:click={() => {
          panelContent = 'bmx';
          panelOpen = true;
        }}
      >
        <img
          src="/what-weve-made/bmx.png"
          alt="BMX Project"
          class="w-full max-h-[325px] object-cover group-hover:-translate-y-8 transition-transform duration-300 select-none"
        />
        <div class="absolute bottom-0 left-0 flex flex-col space-y-2.5 z-10">
          <img src="/wwd/bmx.svg" class="w-10 h-10" alt="BMX" />
          <p class="font-bold text-lg">BMX Project</p>
        </div>
      </button>
    </div>
  </section>

  <HowWeDoIt />

  <!-- <WhatTheySay /> -->

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
