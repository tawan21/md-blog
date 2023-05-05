<script>
  import { fade } from "svelte/transition";

  export let url;
</script>

{#key url}
  <div class="m-4" in:fade>
    <slot />
  </div>
{/key}
