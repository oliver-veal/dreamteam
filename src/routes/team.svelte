<script lang="ts">
  import Menu from '$lib/menu/Menu.svelte';
  import MenuIcon from '$lib/menu/MenuIcon.svelte';
  import { MacScrollbar } from 'fractils';

  let menuOpen = false;

  let closeMenu = () => (menuOpen = false);

  let side_scroll;

  let pos = { top: 0, left: 0, x: 0, y: 0 };

  const mouseDownHandler = (e: MouseEvent) => {
    pos = {
      left: side_scroll.scrollLeft,
      top: side_scroll.scrollTop,
      x: e.clientX,
      y: e.clientY,
    };

    side_scroll.style.cursor = 'grabbing';
    side_scroll.style.userSelect = 'none';

    document.addEventListener('mousemove', mouseMoveHandler);
    document.addEventListener('mouseup', mouseUpHandler);
  };

  const mouseMoveHandler = (e: MouseEvent) => {
    const dx = e.clientX - pos.x;
    const dy = e.clientY - pos.y;

    side_scroll.scrollTop = pos.top - dy;
    side_scroll.scrollLeft = pos.left - dx;
  };

  const mouseUpHandler = (e: MouseEvent) => {
    document.removeEventListener('mousemove', mouseMoveHandler);
    document.removeEventListener('mouseup', mouseUpHandler);

    side_scroll.style.cursor = 'grab';
    side_scroll.style.removeProperty('user-select');
  };
</script>

<MacScrollbar root={side_scroll} disabled={false} />

<div class="w-full h-0 fixed inset-0 flex flex-col justify-between z-50">
  <div
    class="flex items-center justify-between bg-black bg-opacity-75 backdrop-blur-xl p-2.5 md:p-5"
  >
    <a href="/" sveltekit:prefetch>
      <img src="/dreamteam.svg" alt="dreamteam" width="200" />
    </a>
    <button
      on:click={() => {
        menuOpen = !menuOpen;
      }}
      class="p-2"
    >
      <MenuIcon
        bind:open={menuOpen}
        class="w-6 xl:w-8 {menuOpen &&
          '-rotate-90'} transition-transform duration-300"
        fill="#fff"
      />
    </button>
  </div>
</div>

<Menu open={menuOpen} {closeMenu} />

<div
  class="w-full h-screen flex space-x-8 items-center justify-center p-16 py-96"
>
  <h1 class="text-3xl xl:text-8xl uppercase font-light text-right">
    Who we <br /> are
  </h1>
  <h2 class="text-lg xl:text-2xl">
    We are a collection of creatives, <br /> engineers and innovators.
  </h2>
</div>

<div class="min-h-screen w-full flex flex-col">
  <div class="flex w-full flex-grow items-center justify-center">
    <div class="flex w-full max-w-[800px] divide-x py-32">
      <div class="flex flex-col space-y-8 px-16 items-start">
        <div class="flex flex-col">
          <h2 class="text-lg xl:text-3xl">Idan Gal Sohet</h2>
          <p>Branding and Communications</p>
        </div>
        <p class="text-lg xl:text-xl text-justify">
          Idan combines design, engineering and marketing approaches, ensuring
          solutions have a powerful identity that reaches and impacts the
          intended audience.
        </p>
      </div>

      <div
        class="flex flex-col space-y-8 px-16 items-center justify-center flex-shrink-0"
      >
        <h2>Brand Development</h2>
        <h2>Communications</h2>
        <h2>Graphic Design</h2>
      </div>
    </div>
  </div>

  <div
    bind:this={side_scroll}
    on:mousedown={mouseDownHandler}
    class="w-full overflow-x-auto cursor-grab flex justify-center"
  >
    <div class="flex flex-col">
      <div class="flex w-full space-x-16 items-end px-8">
        <div
          class="h-96 min-w-[220px] flex-grow w-full flex-1 rounded-t-full bg-[#ff5470] p-1"
        >
          <img
            src="/headshots/webp/freya_smith.webp"
            alt="Face"
            class="w-full rounded-full"
          />
        </div>

        <div
          class="h-96 min-w-[220px] flex-grow w-full flex-1 rounded-t-full bg-[#ff5470] p-1"
        >
          <img
            src="/headshots/webp/harika.webp"
            alt="Face"
            class="w-full rounded-full"
          />
        </div>

        <div
          class="h-96 min-w-[220px] flex-grow w-full flex-1 rounded-t-full bg-[#ff5470] p-1"
        >
          <img
            src="/headshots/webp/idan.webp"
            alt="Face"
            class="w-full rounded-full"
          />
        </div>

        <div
          class="h-96 min-w-[220px] flex-grow w-full flex-1 rounded-t-full bg-[#ff5470] p-1"
        >
          <img
            src="/headshots/webp/jessica_riley.webp"
            alt="Face"
            class="w-full rounded-full"
          />
        </div>

        <div
          class="h-96 min-w-[220px] flex-grow w-full flex-1 rounded-t-full bg-[#ff5470] p-1"
        >
          <img
            src="/headshots/webp/julian.webp"
            alt="Face"
            class="w-full rounded-full"
          />
        </div>

        <div
          class="h-96 min-w-[220px] flex-grow w-full flex-1 rounded-t-full bg-[#ff5470] p-1"
        >
          <img
            src="/headshots/webp/leo_planck.webp"
            alt="Face"
            class="w-full rounded-full"
          />
        </div>

        <div
          class="h-96 min-w-[220px] flex-grow w-full flex-1 rounded-t-full bg-[#ff5470] p-1"
        >
          <img
            src="/headshots/webp/marco.webp"
            alt="Face"
            class="w-full rounded-full"
          />
        </div>

        <div
          class="h-96 min-w-[220px] flex-grow w-full flex-1 rounded-t-full bg-[#ff5470] p-1"
        >
          <img
            src="/headshots/webp/martin_lombard.webp"
            alt="Face"
            class="w-full rounded-full"
          />
        </div>

        <div
          class="h-96 min-w-[220px] flex-grow w-full flex-1 rounded-t-full bg-[#ff5470] p-1"
        >
          <img
            src="/headshots/webp/oscar_leclercq.webp"
            alt="Face"
            class="w-full rounded-full"
          />
        </div>
      </div>
      <div class="w-full h-32 bg-[#ff5470]" />
    </div>
  </div>
</div>
