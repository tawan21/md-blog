<script>
  // The ordering of these imports is critical to your app working properly
  import "@skeletonlabs/skeleton/themes/theme-crimson.css";
  // If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
  import "@skeletonlabs/skeleton/styles/all.css";
  // Most of your app wide CSS should be put in this file
  import "../app.postcss";
  import { AppBar } from "@skeletonlabs/skeleton";
  import { LightSwitch } from "@skeletonlabs/skeleton";
</script>

<AppBar regionRowMain="font-bold text-3xl" padding="p-5">
  <svelte:fragment slot="lead"><a href="/">.md Blog</a></svelte:fragment>
  <svelte:fragment slot="trail">
    <LightSwitch />
  </svelte:fragment>
</AppBar>
<slot />
