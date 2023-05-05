<script>
  // The ordering of these imports is critical to your app working properly
  import "@skeletonlabs/skeleton/themes/theme-gold-nouveau.css";
  // If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
  import "@skeletonlabs/skeleton/styles/all.css";
  // Most of your app wide CSS should be put in this file
  import "../app.postcss";
  import { autoModeWatcher } from "@skeletonlabs/skeleton";

  import PageTransition from "./transition.svelte";

  import { AppBar, LightSwitch, AppShell } from "@skeletonlabs/skeleton";

  export let data;
</script>

<svelte:head
  >{@html `<script>${autoModeWatcher.toString()} autoModeWatcher();</script>`}</svelte:head
>

<AppShell>
  <svelte:fragment slot="header">
    <AppBar
      gridColumns="grid-cols-1"
      regionRowMain="font-bold text-3xl text-center"
      padding="p-5"
    >
      <a href="/">About Me</a>
    </AppBar>
  </svelte:fragment>
  <PageTransition url={data.url}>
    <slot />
  </PageTransition>
  <svelte:fragment slot="footer">
    <AppBar
      gridColumns="grid-cols-1"
      regionRowMain="font-semibold text-center"
      padding="p-3"
    >
      © 2023 Tawanjot Singh
    </AppBar>
  </svelte:fragment>
</AppShell>
