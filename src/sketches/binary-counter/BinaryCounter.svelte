<script lang="ts">
  import { onDestroy, onMount } from "svelte";

  let counter = 0b0;
  let intervalId: number = 0;

  onMount(() => {
    intervalId = setInterval(() => {
      counter++;
    }, 50);
  });

  onDestroy(() => {
    clearInterval(intervalId);
  });
</script>

<div class="wrapper">
  <div class="counter">{counter.toString(2).padStart(10, "0")}</div>
  <div class="counter">{counter.toString(2).padStart(10, "0")}</div>
  <div class="counter">{counter.toString(2).padStart(10, "0")}</div>
  <div class="counter">{counter.toString(2).padStart(10, "0")}</div>
  <div class="counter">{counter.toString(2).padStart(10, "0")}</div>
</div>

<style>
  .counter {
    font-size: 60px;
    font-family: monospace;
  }
</style>
