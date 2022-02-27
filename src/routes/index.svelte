<script lang="ts">
  import { slide, fade, fly } from 'svelte/transition';

  import Menu from '$lib/logo/menu.svelte';
  import HowWeDoIt from '$lib/sections/how-we-do-it.svelte';
  import WhatsNext from '$lib/sections/whats-next.svelte';
  import WhatWeDo from '$lib/sections/what-we-do.svelte';
  import Mask from '$lib/projects/mask.svelte';
  import { OnMount } from 'fractils';

  import Bmx from '$lib/projects/bmx.svelte';
  import WhoWeAre from '$lib/sections/who-we-are.svelte';
  import Footer from '$lib/sections/footer.svelte';
  import WhatWeveMade from '$lib/sections/what-weve-made.svelte';
  import { spring } from 'svelte/motion';
  import { Parallax, ParallaxLayer } from '$lib/svelte-parallax/index';

  let panelOpen = false;
  let panelContent = 'menu';

  let closeMenu = () => (panelOpen = false);

  let manifesto = spring(0, {
    stiffness: 0.005,
    damping: 0.1,
  });

  let manifesto_open = false;

  $: {
    if (manifesto_open) manifesto.set(100);
    else manifesto.set(0);
  }
</script>

<svelte:window
  on:keydown={(e) => {
    if (e.key === 'Escape') panelOpen = false;
  }}
/>

<head>
  <title> Dreamteam </title>
</head>

<!-- <svg
  xmlns="http://www.w3.org/2000/svg"
  class="absolute inset-0 -z-50 w-screen h-screen"
>
  <defs>
    <clipPath id="manifesto_clip">
      <circle cx="50%" cy="75%" r={$manifesto + 5 + '%'} />
    </clipPath>
  </defs>
</svg> -->

<!-- <svg
  xmlns="http://www.w3.org/2000/svg"
  class="absolute inset-0 -z-50 w-screen h-screen"
>
  <defs>
    <clipPath id="manifesto_button_clip">
      <circle cx="50%" cy="75%" r={(100 - $manifesto) / 21 + '%'} />
    </clipPath>
  </defs>
</svg>

<OnMount>
  <div
    class="absolute inset-0 w-full h-full flex items-center justify-center z-30"
    style="background: linear-gradient(-20deg, rgb(5,255,241) 25%, rgb(255,84,112) 75%); clip-path: url(#manifesto_clip)"
    in:fly={{ y: 150, duration: 1500, delay: 0 }}
  />

  <div
    class="absolute inset-0 w-full h-full flex items-center justify-center z-30 cursor-pointer"
    on:click={() => (manifesto_open = !manifesto_open)}
    style="background: black; clip-path: url(#manifesto_button_clip)"
    in:fly={{ y: 150, duration: 1500, delay: 0 }}
  />
  <div
    class="absolute left-1/2 top-3/4 -translate-x-1/2 -translate-y-1/2"
    in:fly={{ y: 250, duration: 1500, delay: 0 }}
  >
    <p class="pt-64 xl:pt-96">Manifesto</p>
  </div>
</OnMount> -->

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

<main class="space-y-48 xl:space-y-96">
  <div class="relative flex w-full flex-col items-center">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      class="absolute inset-0 -z-50 w-screen h-screen"
    >
      <defs>
        <clipPath id="manifesto_clip">
          <circle cx="50%" cy="75%" r={$manifesto + 5 + '%'} />
        </clipPath>
      </defs>
    </svg>

    <svg
      xmlns="http://www.w3.org/2000/svg"
      class="absolute inset-0 -z-50 w-screen h-screen"
    >
      <defs>
        <clipPath id="manifesto_button_clip">
          <circle cx="50%" cy="75%" r={(100 - $manifesto) / 21 + '%'} />
        </clipPath>
      </defs>
    </svg>

    <OnMount>
      <div class="sticky top-0 left-0 w-full h-screen z-20">
        <div
          class="absolute top-0 left-0 w-full h-screen flex items-center justify-center z-30"
          style="background: linear-gradient(-20deg, rgb(5,255,241) 25%, rgb(255,84,112) 75%); clip-path: url(#manifesto_clip)"
          in:fly={{ y: 150, duration: 1500, delay: 3000 }}
        />

        <div
          class="absolute top-0 left-0 w-full h-full flex items-center justify-center z-30 cursor-pointer"
          on:click={() => (manifesto_open = !manifesto_open)}
          style="background: black; clip-path: url(#manifesto_button_clip)"
          in:fly={{ y: 150, duration: 1500, delay: 3000 }}
        />

        <div
          class="absolute left-1/2 top-3/4 -translate-x-1/2 -translate-y-1/2"
          in:fly={{ y: 250, duration: 1500, delay: 3000 }}
        >
          <p class="pt-64 xl:pt-96">Manifesto</p>
        </div>
      </div>
    </OnMount>

    <div
      class="absolute top-0 flex flex-col w-full h-screen items-center justify-center space-y-8 px-4 xl:px-32"
    >
      <OnMount>
        <h1
          class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16 z-30"
          in:fade={{ duration: 1000, delay: 0 }}
        >
          Design is more than beauty.
        </h1>
        <h1
          class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16 z-30"
          in:fade={{ duration: 1000, delay: 1500 }}
        >
          Engineering is more than science.
        </h1>
      </OnMount>
    </div>

    {#if manifesto_open}
      <div
        class="flex flex-col w-full h-screen items-center justify-center space-y-8 px-4 xl:px-32 z-30"
      >
        <h1
          class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16"
        >
          We know diversity determines innovative futures.
        </h1>
        <h1
          class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16"
        >
          We know design engineering can change the world.
        </h1>
      </div>

      <div
        class="flex flex-col w-full h-screen items-center justify-center space-y-8 px-4 xl:px-32 z-30"
      >
        <h1
          class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16"
        >
          We are tomorrow's designers, engineers, makers and thinkers.
        </h1>
        <h1
          class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16"
        >
          We think freely; paving new ways of thinking and doing.
        </h1>
      </div>

      <div
        class="flex flex-col w-full h-screen items-center justify-center space-y-8 px-4 xl:px-32 z-30"
      >
        <h1
          class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16"
        >
          We engineer the future; incubating tomorrow's change-makers.
        </h1>
        <h1
          class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16"
        >
          We are fearlessly optimistic; radical futures need radical action.
        </h1>
      </div>

      <div
        class="flex flex-col w-full h-screen items-center justify-center space-y-8 px-4 xl:px-32 z-30"
      >
        <h1
          class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16"
        >
          We are defined by innovation.
        </h1>
        <h1
          class="text-3xl xl:text-6xl uppercase font-light text-center px-8 xl:px-16"
        >
          We are defining design engineering.
        </h1>
      </div>
    {/if}
  </div>

  <div class="relative w-full h-screen">
    <Parallax sections={1} threshold={{ top: 0, bottom: 0 }} disabled>
      <ParallaxLayer rate={0.2} style="z-index: 60;">
        <div
          class="flex flex-col w-full h-full items-center justify-center z-30 space-y-12"
        >
          <h1
            class="text-5xl uppercase font-light text-center flex flex-col px-32 select-none"
          >
            We are dream team
          </h1>
          <a href="mailto:contact@dreamteamdesign.co.uk" class="btn">
            <h1 class="uppercase text-xs xl:text-base">Contact</h1>
          </a>
        </div>
      </ParallaxLayer>
      <ParallaxLayer rate={0.15}>
        <div class="flex items-center justify-center">
          <div
            class="rounded-full w-10 xl:w-14 h-10 xl:h-14 absolute left-[75%] top-[37%]"
            style="background: url(/faces/1.png); background-size: cover;"
          />
        </div>
      </ParallaxLayer>
      <ParallaxLayer rate={0.175}>
        <div class="flex items-center justify-center">
          <div
            class="rounded-full w-16 xl:w-20 h-16 xl:h-20 absolute left-[65%] top-[28%]"
            style="background: url(/faces/2.png); background-size: cover;"
          />
        </div>
      </ParallaxLayer>
      <ParallaxLayer rate={0.225}>
        <div class="flex items-center justify-center">
          <div
            class="rounded-full w-24 xl:w-28 h-24 xl:h-28 absolute left-[17.5%] top-[67%]"
            style="background: url(/faces/3.png); background-size: cover;"
          />
        </div>
      </ParallaxLayer>
      <ParallaxLayer rate={0.25}>
        <div class="flex items-center justify-center">
          <div
            class="rounded-full w-28 xl:w-36 h-28 xl:h-36 absolute left-[60%] top-[75%]"
            style="background: url(/faces/4.png); background-size: cover;"
          />
        </div>
      </ParallaxLayer>
      <ParallaxLayer rate={0.275}>
        <div class="flex items-center justify-center">
          <div
            class="rounded-full w-32 xl:w-48 h-32 xl:h-48 absolute left-[20%] top-[16%]"
            style="background: url(/faces/5.png); background-size: cover;"
          />
        </div>
      </ParallaxLayer>
    </Parallax>
  </div>

  <WhatWeDo />

  <WhatWeveMade bind:panelContent bind:panelOpen />

  <HowWeDoIt />

  <!-- <WhatTheySay /> -->

  <WhatsNext />
</main>

<Footer />
