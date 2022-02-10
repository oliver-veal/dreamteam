<script lang="ts">
  import ArrowLeft from '$lib/icon/heroicons/ArrowLeft.js';
  import X from '$lib/icon/heroicons/X.js';

  import Icon from '$lib/icon/Icon.svelte';

  export let open = false;
</script>

<div class="w-full fixed flex items-center justify-end z-40">
  <button on:click={() => (open = false)} class="p-2.5 md:p-5">
    <Icon src={X} class="w-12 xl:w-14" />
  </button>
</div>

<div
  class="min-w-full min-h-full flex p-10 bg-black items-center justify-center mt-4 xl:mt-0"
>
  <div
    class="flex flex-col xl:flex-row space-y-10 xl:space-y-0 xl:space-x-10 items-center justify-center"
  >
    <div class="relative xl:ml-24 mt-12 xl:mt-0">
      <img
        src="/projects/mask/facemask.svg"
        alt="Face Mask Project Logo"
        class="absolute inset-0 w-48 xl:w-72 xl:-translate-x-1/3 -translate-x-[5%] -translate-y-1/4"
      />
      <img
        src="/projects/mask/facemask.png"
        alt="Face Mask Project"
        class="w-full max-h-[411px] object-cover"
      />
    </div>
    <div
      class="flex flex-col space-y-5 max-w-[600px] xl:px-0 xl:max-w-[400px] h-full justify-center"
    >
      <div class="flex flex-col space-y-2.5">
        <h2 class="text-4xl">Design</h2>
        <q class="text-xs">
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
          nonummy
        </q>
      </div>

      <div class="flex flex-col space-y-5">
        <h3 class="text-lg">Brief</h3>
        <p class="text-justify text-sm">
          To find new ways to make students feel safe and at home when they
          arrive at Imperial admist the COVID-19 pandemic.
        </p>
        <h3 class="text-lg">Impact</h3>
        <p class="text-justify text-sm">
          Given that masks are a necessity in public spaces we created a face
          covering that not only provides exceptional protection to students but
          also makes them feel part of the wider Imperial community. We designed
          4 unique designs that represent the values and experiences of Imperial
          students, and our HeiQ Viroblock equipped masks provided a seriously
          high level of protection. In support, we designed a marketing
          campaign, created posters, and directed and filmed a promotional video
          for students. Currently, we have sold over 1000 masks with a reorder
          approved.
        </p>
      </div>
    </div>
  </div>
</div>
