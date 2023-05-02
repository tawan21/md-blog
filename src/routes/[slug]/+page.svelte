<script>
  export let data;

  const formatDate = (dt) => {
    const fmt = new Intl.DateTimeFormat("en", { dateStyle: "medium" });
    return fmt.format(new Date(dt));
  };
</script>

<svelte:head>
  <title>{data.meta.title}</title>
  <meta property="og:type" content="article" />
  <meta property="og:title" content={data.meta.title} />
</svelte:head>

<div class="mt-4 container mx-auto flex flex-col space-y-4">
  <div class="card p-4">
    <header class="card-header p-4">
      <h1>{data.meta.title}</h1>
    </header>
    <div class="mb-4">
      <article class="p-4 space-y-4">
        <p>
          {data.meta.description}
        </p>
        <p>
          <svelte:component this={data.content} />
        </p>
      </article>
      <div class="flex justify-evenly">
        {#each data.meta.categories as category}
          <span class="chip variant-filled">{category}</span>
        {/each}
      </div>
    </div>
    <hr class="opacity-50" />
    <footer class="card-footer p-4">
      <small>on {formatDate(data.meta.date)}</small>
    </footer>
  </div>
</div>
