<script lang="ts">
  import { OnMount } from "fractils";
  import { fly, fade } from "svelte/transition";
  import { spring } from "svelte/motion";

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

<div class="relative flex w-full flex-col items-center min-h-screen">
  <svg
    xmlns="http://www.w3.org/2000/svg"
    class="absolute inset-0 -z-50 w-screen h-screen"
  >
    <defs>
      <clipPath id="manifesto_clip">
        <circle cx="50%" cy="75%" r={$manifesto + 5 + "%"} />
      </clipPath>
    </defs>
  </svg>

  <svg
    xmlns="http://www.w3.org/2000/svg"
    class="absolute inset-0 -z-50 w-screen h-screen"
  >
    <defs>
      <clipPath id="manifesto_button_clip">
        <circle cx="50%" cy="75%" r={(100 - $manifesto) / 21 + "%"} />
      </clipPath>
    </defs>
  </svg>

  <OnMount>
    <div class="sticky top-0 left-0 w-full h-screen z-40">
      <div
        class="gradient absolute top-0 left-0 w-full h-screen flex items-center justify-center z-40"
        style="clip-path: url(#manifesto_clip)"
        in:fly={{ y: 150, duration: 1500, delay: 3000 }}
      />

      <div
        class="absolute top-0 left-0 w-full h-full flex items-center justify-center z-40 cursor-pointer"
        on:click={() => (manifesto_open = !manifesto_open)}
        style="background: black; clip-path: url(#manifesto_button_clip)"
        in:fly={{ y: 150, duration: 1500, delay: 3000, opacity: 1 }}
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
    class="{manifesto_open &&
      'text-black'} absolute top-0 flex flex-col w-full h-screen items-center justify-center space-y-8 px-4 xl:px-32"
  >
    <OnMount>
      <h1 class="z-40" in:fade={{ duration: 1000, delay: 0 }}>
        Design is more than beauty.
      </h1>
      <h1 class="z-40" in:fade={{ duration: 1000, delay: 1500 }}>
        Engineering is more than science.
      </h1>
    </OnMount>
  </div>

  {#if manifesto_open}
    <div
      class="text-black flex flex-col w-full h-screen items-center justify-center space-y-8 px-4 xl:px-32 z-40"
    >
      <h1>We know diversity determines innovative futures.</h1>
      <h1>We know design engineering can change the world.</h1>
    </div>

    <div
      class="text-black flex flex-col w-full h-screen items-center justify-center space-y-8 px-4 xl:px-32 z-40"
    >
      <h1>We are tomorrow's designers, engineers, makers and thinkers.</h1>
      <h1>We think freely; paving new ways of thinking and doing.</h1>
    </div>

    <div
      class="text-black flex flex-col w-full h-screen items-center justify-center space-y-8 px-4 xl:px-32 z-40"
    >
      <h1>We engineer the future; incubating tomorrow's change-makers.</h1>
      <h1>
        We are fearlessly optimistic; radical futures need radical action.
      </h1>
    </div>

    <div
      class="text-black flex flex-col w-full h-screen items-center justify-center space-y-8 px-4 xl:px-32 z-40"
    >
      <h1>We are defined by innovation.</h1>
      <h1>We are defining design engineering.</h1>
    </div>
  {/if}
</div>
