<script lang="ts">
  import { Parallax, ParallaxLayer } from 'svelte-parallax';
</script>

<Parallax sections={1} threshold={{ top: 0 }} style="background-color: black;">
  <ParallaxLayer
    rate={0.1}
    style="display: flex; align-items: start; justify-content: start;"
  >
    <div class="flex w-full h-[40%] justify-center items-center">
      <div class="flex flex-col text-center">
        <h1 class="text-6xl uppercase">How we do it</h1>
      </div>
    </div>
  </ParallaxLayer>

  <ParallaxLayer
    rate={0.2}
    style="display: flex; flex-direction: column; align-items: start; justify-content: start;"
  >
    <div class="flex w-full h-[40%] items-end justify-center">
      <div class="relative w-[971px]">
        <div
          class="absolute inset-0 h-[86px] w-[971px]"
          style="
          background: linear-gradient(-20deg, rgba(255,188,85,1) 0%, rgba(223,0,56,1) 50%, rgba(158,65,208,1) 100%;
          clip-path: url(#hwdi-clip);
        "
        />
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 955 70"
          class="absolute left-[8px] top-[8px] h-[70px] w-[955px]"
        >
          <g>
            <circle cx="35" cy="35" r="35" />
            <circle cx="330" cy="35" r="35" />
            <circle cx="625" cy="35" r="35" />
            <circle cx="920" cy="35" r="35" />
          </g>
        </svg>
      </div>
    </div>
  </ParallaxLayer>

  <ParallaxLayer
    rate={0.3}
    style="display: flex; align-items: end; justify-content: center;"
  >
    <div class="w-[1200px] h-[40%] flex justify-between items-start">
      <div class="w-1/4 px-10 flex flex-col text-center space-y-5">
        <h2 class="font-bold text-3xl">Brief</h2>
        <p>
          You tell us what the challenge is, what you need and why. If you don't
          know the details yet, we can help you define the brief so we know what
          we're aiming to deliver.
        </p>
      </div>
      <div class="w-1/4 px-10 flex flex-col text-center space-y-5">
        <h2 class="font-bold text-3xl">Discover</h2>
        <p>
          Working with you, we scope out the challenge. Through methods like
          desk research, user research, interviews and market research, we
          identify what the challenge context is, helping us to identify and
          prioritise the specific challenges we need to solve and the key
          directions we need to explore.
        </p>
      </div>
      <div class="w-1/4 px-10 flex flex-col text-center space-y-5">
        <h2 class="font-bold text-3xl">Ideation</h2>
        <p>
          We identify potential solutions, illustrating and prototyping the
          possibilities in an iterative and collaborative process with you. We
          test our ideas where necessary to ensure we're confident that we have
          an effective solution.
        </p>
      </div>
      <div class="w-1/4 px-10 flex flex-col text-center space-y-5">
        <h2 class="font-bold text-3xl">Delivery</h2>
        <p>
          We deliver the outcomes as required by the brief. The exact formula
          for what we deliver and how we deliver it depends on the initial
          challenge, but we work closely with you to deliver the solution that
          you need.
        </p>
      </div>
    </div>
  </ParallaxLayer>
</Parallax>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 971 86" class="h-0 w-0">
  <defs>
    <clipPath id="hwdi-clip">
      <path
        class="cls-1"
        d="M928,86a43,43,0,0,1-41.13-30.42A15,15,0,0,0,872.55,45H688.45a15,15,0,0,0-14.32,10.58,43,43,0,0,1-82.26,0A15,15,0,0,0,577.55,45H393.45a15,15,0,0,0-14.32,10.58,43,43,0,0,1-82.26,0A15,15,0,0,0,282.55,45H98.45A15,15,0,0,0,84.13,55.58,43,43,0,1,1,84.28,31,15.34,15.34,0,0,0,99,42H281.65a15.91,15.91,0,0,0,15.19-11.44,43,43,0,0,1,82.32,0A15.91,15.91,0,0,0,394.35,42h182.3a15.91,15.91,0,0,0,15.19-11.44,43,43,0,0,1,82.32,0A15.91,15.91,0,0,0,689.35,42H872a15.34,15.34,0,0,0,14.74-11A43,43,0,1,1,928,86Z"
      />
    </clipPath>
  </defs>
</svg>
