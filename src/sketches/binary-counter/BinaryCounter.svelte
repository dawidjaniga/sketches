<script lang="ts">
  import { onDestroy, onMount } from "svelte";

  export let intervalMs = 50;
  export let delayMs = 0;
  export let length = 10;

  let counter = 0;
  let intervalId: number = 0;

  onMount(() => {
    setTimeout(() => {
      intervalId = setInterval(() => {
        if (counter.toString(2).length < length) {
          counter++;
        } else {
          counter = 0;
        }
      }, intervalMs);
    }, delayMs);
  });

  onDestroy(() => {
    clearInterval(intervalId);
  });
</script>

<div class="wrapper">
  <div class="counter">{counter.toString(2).padStart(length, "0")}</div>
</div>

<style>
  .counter {
    font-size: 60px;
    font-family: monospace;
  }
</style>
