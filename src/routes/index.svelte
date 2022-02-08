<script lang="ts">
  import Button from '$lib/button/Button.svelte';
  import { scale } from 'svelte/transition';

  import ImperialLogo from '$lib/logo/imperial-logo.svelte';
  import Menu from '$lib/logo/menu.svelte';
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
  class="w-full h-full p-10 fixed inset-0 flex flex-col justify-between z-50 pointer-events-none"
  in:scale={{ duration: 1500, start: 0.9, delay: 3000 }}
>
  <div class="flex items-center justify-between">
    <h1 class="text-5xl">
      dream<span class="font-light">team</span>
    </h1>
    <Menu width="30" fill="#fff" />
  </div>
  <div class="flex items-center justify-between">
    <ImperialLogo width="200" fill="#fff" />

    <div class="pointer-events-auto">
      <a href="mailto:contact@dreamteamdesign.co.uk">
        <Button>Contact</Button>
      </a>
    </div>
  </div>
</div>

<Parallax sections={1} threshold={{ top: 0 }} style="background-color: black;">
  <ParallaxLayer
    rate={0.2}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <h1 class="text-6xl uppercase font-light text-center px-16">
      <span in:fade={{ duration: 1000, delay: 0 }}>
        Design is more than beauty.<br />
      </span>
      <span in:fade={{ duration: 1000, delay: 1500 }}>
        Engineering is more than science.
      </span>
    </h1>
  </ParallaxLayer>

  <ParallaxLayer
    rate={0.4}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div
      class="text-white absolute top-3/4 left-1/2 -translate-y-1/2 -translate-x-1/2"
      in:fly={{ y: 150, duration: 1500, delay: 3000 }}
    >
      <Icon src={ChevronDown} size="48" />
    </div>
  </ParallaxLayer>
</Parallax>

<!-- <Manifesto /> -->

<WhoWeAre />

<WhatWeDo />

<WhatWeveMade />

<HowWeDoIt />

<WhatTheySay />

<WhatsNext />
