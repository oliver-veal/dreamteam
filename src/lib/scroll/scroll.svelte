<script lang="ts">
  import { browser } from '$app/env';

  let scrollY: number = browser ? window.scrollY : 0;

  export let start: number;
  export let end: number;

  $: range = end || 0 - start || 0;

  $: s = Math.min(Math.max(0, (scrollY - start) / range || 0), 1);
</script>

<svelte:window bind:scrollY />

<slot {s} />
