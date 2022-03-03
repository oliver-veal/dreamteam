<script lang="ts">
  import Menu from '$lib/menu/Menu.svelte';
  import MenuIcon from '$lib/menu/MenuIcon.svelte';
  import Footer from '$lib/sections/footer.svelte';
  import HowWeDoIt from '$lib/sections/how-we-do-it.svelte';
  import Manifesto from '$lib/sections/manifesto.svelte';
  import ProjectPanel from '$lib/sections/project-panel.svelte';
  import WhatWeDo from '$lib/sections/what-we-do.svelte';
  import WhatWeveMade from '$lib/sections/what-weve-made.svelte';
  import WhatsNext from '$lib/sections/whats-next.svelte';
  import WhoWeAre from '$lib/sections/who-we-are.svelte';

  let panelOpen = false;
  let panelContent = 'menu';

  let closeMenu = () => (panelOpen = false);
</script>

<head>
  <title> Dreamteam </title>
</head>

<div class="w-full h-0 fixed inset-0 flex flex-col justify-between z-[49]">
  <div
    class="flex items-center justify-between bg-black bg-opacity-75 backdrop-blur-xl p-2.5 md:p-5"
  >
    <img src="/dreamteam.svg" alt="dreamteam" width="200" />

    <button
      on:click={() => {
        panelOpen = !panelOpen;
        panelContent = 'menu';
      }}
      class="p-2"
    >
      <MenuIcon
        bind:open={panelOpen}
        class="w-6 xl:w-8 {panelOpen &&
          '-rotate-90'} transition-transform duration-300"
        fill="#fff"
      />
    </button>
  </div>
</div>

<Menu open={panelOpen && panelContent === 'menu'} {closeMenu} />

<ProjectPanel bind:panelContent bind:panelOpen />

<main class="space-y-48 xl:space-y-96">
  <Manifesto />

  <WhoWeAre />

  <WhatWeDo />

  <WhatWeveMade bind:panelContent bind:panelOpen />

  <HowWeDoIt />

  <WhatsNext />
</main>

<Footer />
