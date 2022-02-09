<script lang="ts">
  import { Parallax, ParallaxLayer } from '$lib/svelte-parallax/index';
</script>

<Parallax
  sections={1}
  threshold={{ top: 0, bottom: 1 }}
  style="background-color: black;"
>
  <ParallaxLayer
    rate={0.2}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div class="flex w-full h-full items-center justify-center">
      <h1 class="text-5xl uppercase font-light text-center flex flex-col px-32">
        We are dream team
      </h1>
    </div>
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.15}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div
      class="rounded-full w-10 xl:w-14 h-10 xl:h-14 absolute left-[75%] top-[37%]"
      style="background: url(/faces/1.png); background-size: cover;"
    />
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.175}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div
      class="rounded-full w-16 xl:w-20 h-16 xl:h-20 absolute left-[65%] top-[28%]"
      style="background: url(/faces/2.png); background-size: cover;"
    />
  </ParallaxLayer>

  <ParallaxLayer
    rate={0.225}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div
      class="rounded-full w-24 xl:w-28 h-24 xl:h-28 absolute left-[20%] top-[67%]"
      style="background: url(/faces/3.png); background-size: cover;"
    />
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.25}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div
      class="rounded-full w-28 xl:w-36 h-28 xl:h-36 absolute left-[60%] top-[75%]"
      style="background: url(/faces/4.png); background-size: cover;"
    />
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.275}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div
      class="rounded-full w-32 xl:w-48 h-32 xl:h-48 absolute left-[20%] top-[20%]"
      style="background: url(/faces/5.png); background-size: cover;"
    />
  </ParallaxLayer>
</Parallax>
