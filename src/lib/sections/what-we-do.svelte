<script lang="ts">
  import Icon from '$lib/icon/Icon.svelte';
  import Plus from '$lib/icon/heroicons/Plus.js';

  import { fade } from 'svelte/transition';
  import InformationCircle from '$lib/icon/heroicons/InformationCircle.js';

  let node = '';
</script>

<section
  class="w-full flex flex-col xl:flex-row items-center p-4 space-y-24 xl:space-y-0 transition-all"
  id="what-we-do"
>
  <div
    class="w-full flex flex-col items-center justify-center text-center space-y-8"
  >
    <div class="flex flex-col space-y-4 items-center">
      <h1 class="text-3xl xl:text-6xl uppercase font-light">What we do</h1>

      <div class="flex space-x-4">
        <Icon src={InformationCircle} solid width="20" />
        <h2>Click on a node to find out more</h2>
      </div>
    </div>

    <div class="relative h-[150px] max-w-[350px] w-full">
      {#if node === 'storytelling'}
        <div transition:fade class="absolute top-0 flex flex-col space-y-5">
          <h2 class="text-lg">Storytelling</h2>
          <p>
            We bring products, services and experiences to life through our
            skills in branding, visual communication, graphics, video
            production, marketing and creative direction.
          </p>
        </div>
      {/if}

      {#if node === 'design'}
        <div transition:fade class="absolute top-0 flex flex-col space-y-5">
          <h2 class="text-lg">Design</h2>
          <p>
            We make things that tell a story, fix the problem, lead the way
            through our skills in user-centered design, design for
            manufacturing, 3D modelling, and sustainable design.
          </p>
        </div>
      {/if}

      {#if node === 'engineering'}
        <div transition:fade class="absolute top-0 flex flex-col space-y-5">
          <h2 class="text-lg">Engineering</h2>
          <p>
            We invent new possibilities through our skills in mechanical
            engineering, electronics, robotics, and optimisation.
          </p>
        </div>
      {/if}

      {#if node === 'technology'}
        <div transition:fade class="absolute top-0 flex flex-col space-y-5">
          <h2 class="text-lg">Technology</h2>
          <p>
            We embrace digital innovation through our skills in interaction
            design, user experience design, and machine learning.
          </p>
        </div>
      {/if}
    </div>
  </div>

  <div class="flex w-full h-full justify-center items-center">
    <div
      class="flex w-full sm:w-1/2 h-3/4 sm:h-full items-center justify-center"
    >
      <div class="relative top-0 h-[404px] w-[192px]">
        <div
          class="absolute inset-0 h-[404px] w-[192px]"
          style="
            background: linear-gradient(-20deg, rgba(255,188,85,1) 0%, rgba(223,0,56,1) 50%, rgba(158,65,208,1) 100%);
            clip-path: url(#wwd-clip);
          "
        />

        <button
          class="group flex items-center justify-center absolute left-[13px] top-[3px] w-[61px] h-[60px] rounded-full bg-black hover:bg-transparent text-black hover:text-white transition-colors"
          on:click={() => (node = 'storytelling')}
        >
          <div
            class="group-hover:text-white absolute text-transparent xl:-translate-x-80 translate-x-16 xl:right-0 left-0 transition-all select-none pointer-events-none"
          >
            <h1 class="text-xl xl:text-3xl">Storytelling</h1>
          </div>
          <Icon src={Plus} width="24" />
        </button>
        <button
          class="group flex items-center justify-center absolute left-[128px] top-[94px] w-[61px] h-[60px] rounded-full bg-black hover:bg-transparent text-black hover:text-white transition-colors"
          on:click={() => (node = 'design')}
        >
          <div
            class="group-hover:text-white absolute text-transparent xl:translate-x-16 -translate-x-16 xl:left-0 right-0 transition-all select-none pointer-events-none"
          >
            <h1 class="text-xl xl:text-3xl">Design</h1>
          </div>
          <Icon src={Plus} width="24" />
        </button>
        <button
          class="group flex items-center justify-center absolute left-[2px] top-[245px] w-[61px] h-[60px] rounded-full bg-black hover:bg-transparent text-black hover:text-white transition-colors"
          on:click={() => (node = 'engineering')}
        >
          <div
            class="group-hover:text-white absolute text-transparent xl:-translate-x-80 translate-x-16 xl:right-0 left-0 transition-all select-none pointer-events-none"
          >
            <h1 class="text-xl xl:text-3xl">Engineering</h1>
          </div>
          <Icon src={Plus} width="24" />
        </button>
        <button
          class="group flex items-center justify-center absolute left-[84px] top-[341px] w-[61px] h-[60px] rounded-full bg-black hover:bg-transparent text-black hover:text-white transition-colors"
          on:click={() => (node = 'technology')}
        >
          <div
            class="group-hover:text-white absolute text-transparent xl:translate-x-16 -translate-x-16 xl:left-0 right-0 transition-all select-none pointer-events-none"
          >
            <h1 class="text-xl xl:text-3xl">Technology</h1>
          </div>
          <Icon src={Plus} width="24" />
        </button>
      </div>
    </div>
  </div>
</section>

<svg
  xmlns="http://www.w3.org/2000/svg"
  viewBox="0 0 192 404"
  class="absolute inset-0 w-full h-full -z-50"
>
  <defs>
    <clipPath id="wwd-clip">
      <path
        d="M159.12,157.1a33.12,33.12,0,0,1-13.55-2.89A13.53,13.53,0,0,0,130,157.3L63.9,243.52A13.34,13.34,0,0,0,62,259.07a33,33,0,0,1-2.49,36.17,8.46,8.46,0,0,0,.32,10.61l29.4,34.35a8.32,8.32,0,0,0,10.29,1.86,33.18,33.18,0,1,1-11.21,9.77,8.23,8.23,0,0,0-.46-10.16L58.14,307a8.54,8.54,0,0,0-10.34-2,33.09,33.09,0,1,1-.92-59.79A13.39,13.39,0,0,0,62.26,242l66.08-86.19a13.37,13.37,0,0,0,1.89-15.58,33.22,33.22,0,0,1-2.18-27.71,13.14,13.14,0,0,0-4.27-14.86L77.72,61.36A13.42,13.42,0,0,0,62,60.71,33.09,33.09,0,1,1,74.83,44.36a13.48,13.48,0,0,0,4.3,15.22l45.93,36.15a13.47,13.47,0,0,0,15.79.61,33.13,33.13,0,1,1,18.27,60.76Z"
      />
    </clipPath>
  </defs>
</svg>
