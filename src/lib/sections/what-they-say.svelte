<script lang="ts">
  import { Parallax, ParallaxLayer } from 'svelte-parallax';
</script>

<Parallax sections={1} threshold={{ top: 0 }} style="background-color: black;">
  <ParallaxLayer
    rate={0.15}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div class="flex w-full h-full">
      <div class="flex w-1/2 items-center justify-center">
        <h1
          class="text-6xl uppercase font-light text-center flex flex-col px-32"
        >
          What they say
        </h1>
      </div>
    </div>
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.35}
    style="display: flex; align-items: center; justify-content: end;"
  >
    <div class="flex w-1/2 h-full flex-col items-center justify-center">
      <div class="flex p-10 space-x-20 items-center">
        <img
          src="/faces/5.png"
          alt="Mazdak Ghajri"
          class="rounded-full w-40 h-40"
        />
        <div class="flex flex-col space-y-5">
          <h1 class="font-bold text-3xl max-w-[80%]">
            <q>
              Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
              nonummy
            </q>
          </h1>
          <div class="flex flex-col">
            <b>Mazdak Ghajri</b>
            <p>Client - Blast Injury Conference</p>
          </div>
        </div>
      </div>

      <div class="flex p-10 space-x-20 items-center">
        <img
          src="/faces/4.png"
          alt="Mazdak Ghajri"
          class="rounded-full w-40 h-40"
        />
        <div class="flex flex-col space-y-5">
          <h1 class="font-bold text-3xl max-w-[80%]">
            <q>
              Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
              nonummy
            </q>
          </h1>
          <div class="flex flex-col">
            <b>Mazdak Ghajri</b>
            <p>Client - Blast Injury Conference</p>
          </div>
        </div>
      </div>

      <div class="flex p-10 space-x-20 items-center">
        <img
          src="/faces/3.png"
          alt="Mazdak Ghajri"
          class="rounded-full w-40 h-40"
        />
        <div class="flex flex-col space-y-5">
          <h1 class="font-bold text-3xl max-w-[80%]">
            <q>
              Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
              nonummy
            </q>
          </h1>
          <div class="flex flex-col">
            <b>Mazdak Ghajri</b>
            <p>Client - Blast Injury Conference</p>
          </div>
        </div>
      </div>
    </div>
  </ParallaxLayer>
</Parallax>
