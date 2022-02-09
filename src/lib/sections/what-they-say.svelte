<script lang="ts">
  import { Parallax, ParallaxLayer } from '$lib/svelte-parallax/index';
</script>

<Parallax
  sections={1}
  threshold={{ top: 0, bottom: 1 }}
  style="background-color: black;"
>
  <ParallaxLayer rate={0.15}>
    <div class="flex w-full h-full justify-end items-end">
      <div class="flex w-full h-full">
        <div class="flex w-full h-1/2 items-center justify-center">
          <h1
            class="text-3xl xl:text-6xl uppercase font-light text-center flex flex-col xl:px-32"
          >
            What they say
          </h1>
        </div>
      </div>
    </div>
  </ParallaxLayer>
  <ParallaxLayer rate={0.35}>
    <div class="flex w-full h-full justify-center items-end">
      <div
        class="flex w-full max-w-[400px] sm:max-w-[800px] xl:max-w-[1100px] h-3/4 flex-col items-center justify-center xl:p-24 sm:p-8 p-2"
      >
        <div
          class="flex p-2.5 sm:p-6 xl:p-10 space-x-5 sm:space-x-10 xl:space-x-20 items-center"
        >
          <img
            src="/faces/5.png"
            alt="Mazdak Ghajri"
            class="rounded-full w-16 sm:w-24 xl:w-40 sm:h-24 h-16 xl:h-40"
          />
          <div class="flex flex-col space-y-2.5">
            <h1 class="font-bold text-base sm:text-2xl xl:text-3xl">
              <q>
                Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed
                diam nonummy
              </q>
            </h1>
            <div class="flex flex-col text-sm">
              <b>Mazdak Ghajri</b>
              <p>Client - Blast Injury Conference</p>
            </div>
          </div>
        </div>

        <div
          class="flex p-2.5 sm:p-6 xl:p-10 space-x-5 sm:space-x-10 xl:space-x-20 items-center"
        >
          <img
            src="/faces/4.png"
            alt="Mazdak Ghajri"
            class="rounded-full w-16 sm:w-24 xl:w-40 sm:h-24 h-16 xl:h-40"
          />
          <div class="flex flex-col space-y-2.5">
            <h1 class="font-bold text-base sm:text-2xl xl:text-3xl">
              <q>
                Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed
                diam nonummy
              </q>
            </h1>
            <div class="flex flex-col text-sm">
              <b>Mazdak Ghajri</b>
              <p>Client - Blast Injury Conference</p>
            </div>
          </div>
        </div>

        <div
          class="flex p-2.5 sm:p-6 xl:p-10 space-x-5 sm:space-x-10 xl:space-x-20 items-center"
        >
          <img
            src="/faces/3.png"
            alt="Mazdak Ghajri"
            class="rounded-full w-16 sm:w-24 xl:w-40 sm:h-24 h-16 xl:h-40"
          />
          <div class="flex flex-col space-y-2.5">
            <h1 class="font-bold text-base sm:text-2xl xl:text-3xl">
              <q>
                Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed
                diam nonummy
              </q>
            </h1>
            <div class="flex flex-col text-sm">
              <b>Mazdak Ghajri</b>
              <p>Client - Blast Injury Conference</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </ParallaxLayer>
</Parallax>
