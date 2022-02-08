<script lang="ts">
  import { Parallax, ParallaxLayer } from 'svelte-parallax';
</script>

<Parallax sections={1} threshold={{ top: 0 }} style="background-color: black;">
  <ParallaxLayer
    rate={0.15}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div class="flex w-full h-full justify-center">
      <div class="flex flex-col text-center">
        <h1 class="text-2xl uppercase font-light pt-32">What we've made</h1>
        <p>A small glimpse at our work</p>
      </div>
    </div>
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.25}
    style="display: flex; flex-direction: column; align-items: center; justify-content: center;"
  >
    <div class="flex w-full items-center justify-center">
      <div class="relative flex h-[325px] w-[300px] items-end">
        <div
          class="w-full h-full absolute"
          style="background: url(/wwd/mask.png) right bottom; clip-path: url(#oval-clip);"
        />
      </div>
      <div class="relative flex h-[325px] w-[300px] items-end">
        <div
          class="w-full h-full absolute"
          style="background: url(/wwd/bic.png) right; clip-path: url(#oval-clip);"
        />
      </div>
      <div class="relative flex h-[325px] w-[300px] items-end">
        <div
          class="w-full h-full absolute"
          style="background: url(/wwd/bmx.png) right top; clip-path: url(#oval-clip);"
        />
      </div>
    </div>
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.35}
    style="display: flex; flex-direction: column; align-items: center; justify-content: center;"
  >
    <div class="flex w-full items-center justify-center">
      <div
        class="relative flex h-[325px] w-[300px] items-end cursor-pointer hover:pb-8 transition-all duration-300"
      >
        <div class="flex flex-col space-y-2.5 z-10 pb-10">
          <img src="/wwd/mask.svg" class="w-10 h-10" alt="Mask" />
          <p class="font-bold text-lg">Imperial Face Mask</p>
        </div>
      </div>
      <div
        class="relative flex h-[325px] w-[300px] items-end cursor-pointer hover:pb-8 transition-all duration-300"
      >
        <div class="flex flex-col space-y-2.5 z-10 pb-10">
          <img src="/wwd/bic.svg" class="w-10 h-10" alt="BIC" />
          <p class="font-bold text-lg">Blast Injury Conference</p>
        </div>
      </div>
      <div
        class="relative flex h-[325px] w-[300px] items-end cursor-pointer hover:pb-8 transition-all duration-300"
      >
        <div class="flex flex-col space-y-2.5 z-10 pb-10">
          <img src="/wwd/bmx.svg" class="w-10 h-10" alt="BMX" />
          <p class="font-bold text-lg">BMX Project</p>
        </div>
      </div>
    </div>
  </ParallaxLayer>
</Parallax>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 189 308" class="w-0 h-0">
  <defs>
    <clipPath id="oval-clip">
      <ellipse
        rx="168.9"
        ry="64.37"
        transform="translate(200, 160) rotate(-63.76)"
      />
    </clipPath>
  </defs>
</svg>
