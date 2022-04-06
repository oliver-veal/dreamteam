<script lang="ts">
  import Bmx from "$lib/projects/bmx.svelte";

  import Mask from "$lib/projects/mask.svelte";

  import { fade } from "svelte/transition";
  export let panelContent: string;
  export let panelOpen: boolean;
</script>

{#if panelOpen}
  <div
    transition:fade
    class="fixed inset-0  w-screen h-screen bg-black bg-opacity-75 backdrop-blur-xl overflow-y-auto z-40"
  >
    <div class="min-h-screen flex flex-col justify-center items-center pt-16">
      <div transition:fade>
        {#if panelContent === "mask"}
          <Mask />
        {:else if panelContent === "bmx"}
          <Bmx />
        {/if}
      </div>
    </div>
  </div>
{/if}
