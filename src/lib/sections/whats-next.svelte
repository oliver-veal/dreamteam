<script lang="ts">
  import { Parallax, ParallaxLayer } from '$lib/svelte-parallax/index';
</script>

<Parallax
  sections={1.1}
  threshold={{ top: 0, bottom: 0 }}
  style="background-color: black;"
>
  <ParallaxLayer
    rate={0.1}
    style="display: flex; align-items: start; justify-content: start;"
  >
    <div class="flex w-full h-[25%] xl:h-[40%] justify-center items-center">
      <div class="flex flex-col text-center">
        <h1 class="text-3xl xl:text-6xl uppercase">What's Next</h1>
      </div>
    </div>
  </ParallaxLayer>

  <ParallaxLayer
    rate={0.2}
    style="display: flex; flex-direction: column; align-items: start; justify-content: start;"
  >
    <div class="flex w-full h-[30%] xl:h-[45%] items-end justify-center">
      <div class="flex w-full space-x-8 xl:space-x-48">
        <div class="flex w-1/2 justify-end">
          <img src="/next/butterfly.svg" class="w-16 h-16" alt="Butterfly" />
        </div>
        <div class="flex w-1/2 justify-start">
          <img src="/next/penta.svg" class="w-16 h-16" alt="Penta" />
        </div>
      </div>
    </div>
  </ParallaxLayer>

  <ParallaxLayer
    rate={0.3}
    style="display: flex; align-items: end; justify-content: center;"
  >
    <div class="w-full h-[60%] xl:h-[50%] flex justify-between items-start p-5">
      <div class="flex w-full space-x-8 xl:space-x-48">
        <div class="flex flex-col w-1/2 items-end space-y-5 sm:space-y-10">
          <h2 class="text-2xl">Butterfly</h2>
          <div class="flex flex-col text-right">
            <p>Product Design</p>
            <p>UI / UX</p>
            <p>Experience</p>
          </div>
          <div class="flex flex-col text-right sm:max-w-[60%]">
            <p class="text-sm sm:text-base">
              Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
              nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam
              erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci
              tation ullamcorper suscipit lobortis nisl
            </p>
          </div>
        </div>
        <div class="flex flex-col w-1/2 items-start space-y-5 sm:space-y-10">
          <h2 class="text-2xl">Penta</h2>
          <div class="flex flex-col text-left">
            <p>Logo Design</p>
            <p>Strategy</p>
            <p>Website</p>
          </div>
          <div class="flex flex-col text-left sm:max-w-[60%]">
            <p class="text-sm sm:text-base">
              Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
              nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam
              erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci
              tation ullamcorper suscipit lobortis nisl
            </p>
          </div>
        </div>
      </div>
    </div>
  </ParallaxLayer>
</Parallax>
