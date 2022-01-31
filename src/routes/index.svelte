<script lang="ts">
  import { browser } from '$app/env';
  import { fade, scale, fly } from 'svelte/transition';
  import { Parallax, ParallaxLayer } from 'svelte-parallax';

  import Button from '$lib/button/Button.svelte';
  import Icon from '$lib/icon/Icon.svelte';
  import Scroll from '$lib/scroll/scroll.svelte';

  import ImperialLogo from '$lib/logo/imperial-logo.svelte';
  import Menu from '$lib/logo/menu.svelte';
  import ChevronDown from '$lib/icon/heroicons/ChevronDown.js';
  import Plus from '$lib/icon/heroicons/Plus.js';

  let innerHeight: number = browser ? window.innerHeight : 0;
</script>

<svelte:window bind:innerHeight on:load={() => window.scrollTo({ top: 0 })} />
<!-- <svelte:window bind:innerHeight /> -->

<head>
  <title> Dreamteam </title>
</head>

<div
  class="w-full h-full p-10 fixed inset-0 flex flex-col justify-between z-50 pointer-events-none"
  in:scale={{ duration: 1500, start: 0.9, delay: 3000 }}
>
  <div class="flex items-center justify-between">
    <h1 class="text-5xl">
      dream<span class="font-light">team</span>
    </h1>
    <Menu width="30" fill="#fff" />
  </div>
  <div class="flex items-center justify-between">
    <ImperialLogo width="200" fill="#fff" />

    <div class="pointer-events-auto">
      <Button>Contact</Button>
    </div>
  </div>
</div>

<div class="fixed top-0 w-full h-screen flex items-center justify-center -z-50">
  <h1 class="text-6xl uppercase font-light text-center px-16">
    <span in:fade={{ duration: 1000, delay: 0 }}
      >Design is more than beauty.<br /></span
    >
    <span in:fade={{ duration: 1000, delay: 1500 }}
      >Engineering is more than science.</span
    >
  </h1>
  <div
    class="text-white absolute top-3/4 left-1/2 -translate-y-1/2 -translate-x-1/2"
    in:fly={{ y: 150, duration: 1500, delay: 3000 }}
  >
    <Icon src={ChevronDown} size="48" />
  </div>
</div>

<Scroll start={0} end={innerHeight} let:s>
  <svg class="fixed inset-0 w-full h-full">
    <defs>
      <clipPath id="clip">
        <circle cx="50%" cy="75%" r="{s * 100}%" />
      </clipPath>
    </defs>
  </svg>
</Scroll>

<div class="w-full">
  <div
    class="h-screen w-full sticky inset-0 -z-10"
    style="
            background: linear-gradient(-45deg, rgba(255,188,85,1) 0%, rgba(223,0,56,1) 50%, rgba(158,65,208,1) 100%;
            background-position: 0.25;
            clip-path: url(#clip);
          "
  />

  <Parallax sections={2.5} threshold={{ top: 0 }}>
    <ParallaxLayer
      rate={0.1}
      style="display: flex; align-items: center; justify-content: center;"
    >
      <h1
        class="text-4xl uppercase font-light text-center flex flex-col px-32 space-y-16"
      >
        <span>We know diversity determines innovative futures.</span>
        <span>We know design engineering can change the world.</span>
      </h1>
    </ParallaxLayer>

    <ParallaxLayer
      rate={0.2}
      offset={0.5}
      style="display: flex; align-items: center; justify-content: center;"
    >
      <h1
        class="text-4xl uppercase font-light text-center flex flex-col px-32 space-y-16"
      >
        <span>
          We are tomorrow's designers, engineers, makers and thinkers.
        </span>
        <span>We think freely; paving new ways of thinking and doing. </span>
      </h1>
    </ParallaxLayer>

    <ParallaxLayer
      rate={0.3}
      offset={1}
      style="display: flex; align-items: center; justify-content: center;"
    >
      <h1
        class="text-4xl uppercase font-light text-center flex flex-col px-32 space-y-16"
      >
        <span>
          We engineer the future; incubating tomorrow's change-makers.
        </span>
        <span>
          We are fearlessly optimistic; radical futures need radical action.
        </span>
      </h1>
    </ParallaxLayer>

    <ParallaxLayer
      rate={0.4}
      offset={1.5}
      style="display: flex; align-items: center; justify-content: center;"
    >
      <h1
        class="text-4xl uppercase font-light text-center flex flex-col px-32 space-y-16"
      >
        <span>We are defined by innovation.</span>
        <span>We are defining design engineering. </span>
      </h1>
    </ParallaxLayer>
  </Parallax>
</div>

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

<Parallax sections={1} threshold={{ top: 0 }} style="background-color: black;">
  <ParallaxLayer
    rate={0.15}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div class="flex w-full h-full">
      <div class="flex w-1/2 items-center justify-end">
        <h1
          class="text-6xl uppercase font-light text-center flex flex-col px-32"
        >
          What we do
        </h1>
      </div>
    </div>
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.35}
    style="display: flex; flex-direction: column; align-items: center; justify-content: center;"
  >
    <div class="flex w-full h-full justify-end">
      <div class="flex w-1/2 items-center justify-start pl-32 z-50">
        <div
          class="relative h-[404px] w-[192px]"
          style="
      background: linear-gradient(-20deg, rgba(255,188,85,1) 0%, rgba(223,0,56,1) 50%, rgba(158,65,208,1) 100%;
      clip-path: url(#wwd-clip);
      "
        >
          <button
            class="flex items-center justify-center absolute left-[13px] top-[3px] w-[61px] h-[60px] rounded-full bg-black hover:bg-transparent text-black hover:text-white transition-colors"
          >
            <Icon src={Plus} width="24" />
          </button>
          <button
            class="flex items-center justify-center absolute left-[128px] top-[94px] w-[61px] h-[60px] rounded-full bg-black hover:bg-transparent text-black hover:text-white transition-colors"
          >
            <Icon src={Plus} width="24" />
          </button>
          <button
            class="flex items-center justify-center absolute left-[2px] top-[245px] w-[61px] h-[60px] rounded-full bg-black hover:bg-transparent text-black hover:text-white transition-colors"
          >
            <Icon src={Plus} width="24" />
          </button>
          <button
            class="flex items-center justify-center absolute left-[84px] top-[341px] w-[61px] h-[60px] rounded-full bg-black hover:bg-transparent text-black hover:text-white transition-colors"
          >
            <Icon src={Plus} width="24" />
          </button>
        </div>
      </div>
    </div>
  </ParallaxLayer>
</Parallax>

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
      <div class="relative flex h-[325px] w-[300px] items-end">
        <div class="flex flex-col space-y-2.5 z-10 pb-10">
          <img src="/wwd/mask.svg" class="w-10 h-10" alt="Mask" />
          <p class="font-bold text-lg">Imperial Face Mask</p>
        </div>
      </div>
      <div class="relative flex h-[325px] w-[300px] items-end">
        <div class="flex flex-col space-y-2.5 z-10 pb-10">
          <img src="/wwd/bic.svg" class="w-10 h-10" alt="BIC" />
          <p class="font-bold text-lg">Blast Injury Conference</p>
        </div>
      </div>
      <div class="relative flex h-[325px] w-[300px] items-end">
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

<Parallax sections={1} threshold={{ top: 0 }} style="background-color: black;">
  <ParallaxLayer
    rate={0.1}
    style="display: flex; align-items: center; justify-content: center;"
  >
    <div class="flex w-full h-full justify-center">
      <div class="flex flex-col text-center">
        <h1 class="text-6xl uppercase pt-48">How we do it</h1>
      </div>
    </div>
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.2}
    style="display: flex; flex-direction: column; align-items: center; justify-content: center;"
  >
    <div class="flex w-full h-full items-start justify-center pt-96">
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
    style="display: flex; flex-direction: column; align-items: center; justify-content: center;"
  >
    <div class="flex w-full h-full items-start justify-center pt-[450px]">
      <div
        class="relative h-[86px] w-[1200px] flex items-center justify-between"
      >
        <h2 class="font-bold text-3xl text-center w-1/4">Brief</h2>
        <h2 class="font-bold text-3xl text-center w-1/4">Discover</h2>
        <h2 class="font-bold text-3xl text-center w-1/4">Ideation</h2>
        <h2 class="font-bold text-3xl text-center w-1/4">Delivery</h2>
      </div>
    </div>
  </ParallaxLayer>
  <ParallaxLayer
    rate={0.4}
    style="display: flex; flex-direction: column; align-items: center; justify-content: center;"
  >
    <div class="flex w-full h-full items-start justify-center pt-[550px]">
      <div class="relative w-[1200px] flex justify-between text-center">
        <p class="w-1/4 px-10">
          You tell us what the challenge is, what you need and why. If you don't
          know the details yet, we can help you define the brief so we know what
          we're aiming to deliver.
        </p>
        <p class="w-1/4 px-10">
          Working with you, we scope out the challenge. Through methods like
          desk research, user research, interviews and market research, we
          identify what the challenge context is, helping us to identify and
          prioritise the specific challenges we need to solve and the key
          directions we need to explore.
        </p>
        <p class="w-1/4 px-10">
          We identify potential solutions, illustrating and prototyping the
          possibilities in an iterative and collaborative process with you. We
          test our ideas where necessary to ensure we're confident that we have
          an effective solution.
        </p>
        <p class="w-1/4 px-10">
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
