<script lang="ts">
  import { Button } from "m3-svelte";
  import { loadFile } from "$lib/state";

  let chooser: HTMLInputElement;
</script>

<h1 class="my-6 text-5xl md:text-9xl">RatPoison</h1>
<p class="my-2 flex-col lg:flex">
  <span>
    RatPoison is a Minecraft RAT Detector based off of RatRater2. 
  </span>
  <span>Drag and Drop, paste, or...</span>
</p>
<input
  type="file"
  bind:this={chooser}
  class="hidden"
  on:change={() => {
    const file = chooser.files && chooser.files[0];
    if (!file) return;
    loadFile(file);
  }}
/>
<Button type="filled" on:click={() => chooser.click()}>Choose a file</Button>
<p class="mt-auto">
  Made by @Czcx using code from @KTibow
</p>
