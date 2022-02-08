<script lang="ts">
  import { Parallax, ParallaxLayer } from 'svelte-parallax';
</script>

<Parallax sections={1} threshold={{ top: 0 }} style="background-color: black;">
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
      class="rounded-full w-14 h-14 absolute left-[75%] top-[37%]"
      style="background: url(/faces/1.png); background-size: cover;"
    />
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.175}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div
      class="rounded-full w-20 h-20 absolute left-[65%] top-[28%]"
      style="background: url(/faces/2.png); background-size: cover;"
    />
  </ParallaxLayer>

  <ParallaxLayer
    rate={0.225}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div
      class="rounded-full w-28 h-28 absolute left-[30%] top-[67%]"
      style="background: url(/faces/3.png); background-size: cover;"
    />
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.25}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div
      class="rounded-full w-36 h-36 absolute left-[60%] top-[75%]"
      style="background: url(/faces/4.png); background-size: cover;"
    />
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.275}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div
      class="rounded-full w-48 h-48 absolute left-[20%] top-[30%]"
      style="background: url(/faces/5.png); background-size: cover;"
    />
  </ParallaxLayer>
</Parallax>
