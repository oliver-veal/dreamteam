<script lang="ts">
  import { draw } from "svelte/transition";

  export let open = false;
  export let color = "#fff";
</script>

<svg
  xmlns="http://www.w3.org/2000/svg"
  viewBox="0 0 20 20"
  fill={color}
  {...$$restProps}
>
  {#if open}
    <path
      transition:draw={{ duration: 300 }}
      d="M 2.5 2.5 L 17.5 17.5"
      stroke-linecap="round"
      stroke-linejoin="round"
      stroke-width="5"
      stroke={color}
    />
    <path
      transition:draw={{ duration: 300 }}
      d="M 17.5 2.5 L 2.5 17.5"
      stroke-linecap="round"
      stroke-linejoin="round"
      stroke-width="5"
      stroke={color}
    />
  {/if}

  <circle cx="2.5" cy="2.5" r="2.5" />
  <circle cx="17.5" cy="2.5" r="2.5" />
  <circle cx="2.5" cy="17.5" r="2.5" />
  <circle cx="17.5" cy="17.5" r="2.5" />
</svg>
