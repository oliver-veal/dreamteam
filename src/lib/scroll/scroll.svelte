<script lang="ts">
  import { browser } from '$app/env';
  import { spring } from 'svelte/motion';

  let scrollY: number = browser ? window.scrollY : 0;

  export let start: number;
  export let end: number;

  $: range = (end || 0) - (start || 0);

  const coord = spring(undefined, { stiffness: 0.017, damping: 0.26 });

  $: {
    let current = Math.min(Math.max(0, (scrollY - start) / range || 0), 1);
    coord.set(current);
  }

  $: s = $coord;
</script>

<svelte:window bind:scrollY />

<slot {s} />
