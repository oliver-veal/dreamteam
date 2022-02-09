<script lang="ts">
  import Button from '$lib/button/Button.svelte';
  import { scale } from 'svelte/transition';

  import ImperialLogo from '$lib/logo/imperial-logo.svelte';
  import Menu from '$lib/logo/menu.svelte';
  import Hero from '$lib/sections/hero.svelte';
  import WhatWeveMade from '$lib/sections/what-weve-made.svelte';
  import HowWeDoIt from '$lib/sections/how-we-do-it.svelte';
  import WhatTheySay from '$lib/sections/what-they-say.svelte';
  import WhatsNext from '$lib/sections/whats-next.svelte';
  import WhatWeDo from '$lib/sections/what-we-do.svelte';
  import WhoWeAre from '$lib/sections/who-we-are.svelte';
  // import Manifesto from '$lib/sections/manifesto.svelte';
</script>

<head>
  <title> Dreamteam </title>
</head>

<div class="w-full h-0 fixed inset-0 flex flex-col justify-between z-10">
  <div
    class="flex items-center justify-between bg-black bg-opacity-75 backdrop-blur-lg p-2.5 md:p-5 lg:p-10"
  >
    <h1 class="text-3xl lg:text-5xl">
      dream<span class="font-light">team</span>
    </h1>
    <Menu class="w-6 lg:w-8" fill="#fff" />
  </div>
</div>

<!-- <Manifesto /> -->

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
  class="px-12 p-24 lg:p-48 flex flex-col sm:flex-row space-y-12 sm:space-y-0 justify-between items-center"
  style="background: linear-gradient(-20deg, rgb(5,255,241) 25%, rgb(255,84,112) 75%; z-index: 60;"
>
  <div class="flex flex-col sm:space-y-2">
    <b class="uppercase font-bold">Contact</b>
    <p>DreamTeam London</p>
    <p>South Kensington</p>
    <p>04 56784900</p>
  </div>
  <p>All Rights Reserved</p>
</footer>
