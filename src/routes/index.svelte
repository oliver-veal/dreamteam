<script lang="ts">
  // import Button from '$lib/button/Button.svelte';

  import { slide, fly, scale } from 'svelte/transition';

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
  // import Manifesto from '$lib/sections/manifesto.svelte';

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
    <h1 class="text-3xl lg:text-5xl select-none">
      dream<span class="font-light">team</span>
    </h1>
    <button on:click={() => (menuOpen = !menuOpen)} class="p-2">
      <Menu
        bind:open={menuOpen}
        class="w-6 lg:w-8 {menuOpen &&
          '-rotate-90'} transition-transform duration-300"
        fill="#fff"
      />
    </button>
  </div>
</div>

<!-- <Manifesto /> -->

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

<main class="space-y-48 lg:space-y-96">
  <Hero />

  <WhoWeAre />

  <WhatWeDo />

  <WhatWeveMade />

  <HowWeDoIt />

  <WhatTheySay />

  <WhatsNext />
</main>

<footer
  class="px-12 p-24 lg:p-48 flex flex-col sm:flex-row space-y-12 sm:space-y-0 justify-between items-center z-50"
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
