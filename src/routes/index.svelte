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

  import Icon from '$lib/icon/Icon.svelte';
  import ChevronDown from '$lib/icon/heroicons/ChevronDown.js';

  import { Parallax, ParallaxLayer } from 'svelte-parallax';
  import { fade, fly } from 'svelte/transition';
</script>

<head>
  <title> Dreamteam </title>
</head>

<div
  class="w-full h-full p-2.5 xl:p-10 fixed inset-0 flex flex-col justify-between z-50 pointer-events-none"
  in:scale={{ duration: 1500, start: 0.9, delay: 3000 }}
>
  <div class="flex items-center justify-between">
    <h1 class="text-3xl xl:text-5xl">
      dream<span class="font-light">team</span>
    </h1>
    <Menu class="w-6 xl:w-8" fill="#fff" />
  </div>
  <div class="flex items-center justify-between">
    <ImperialLogo class="w-[100px] xl:w-[200px]" fill="#fff" />

    <div class="pointer-events-auto">
      <a href="mailto:contact@dreamteamdesign.co.uk">
        <Button>Contact</Button>
      </a>
    </div>
  </div>
</div>

<!-- <Manifesto /> -->

<main class="space-y-48">
  <Hero />

  <WhoWeAre />

  <WhatWeDo />

  <WhatWeveMade />

  <HowWeDoIt />

  <WhatTheySay />

  <WhatsNext />
</main>
