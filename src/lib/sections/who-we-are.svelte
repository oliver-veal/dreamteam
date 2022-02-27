<script lang="ts">
  import { Parallax, ParallaxLayer } from '$lib/svelte-parallax/index';
  import Button from '$lib/button/Button.svelte';
</script>

<Parallax sections={1} threshold={{ top: 0, bottom: 0 }}>
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
