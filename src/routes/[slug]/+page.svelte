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

<div class="max-w-6xl mx-auto flex flex-col space-y-4">
  <header class="card-header px-4">
    <h1>{data.meta.title}</h1>
  </header>
  <div>
    <article class="p-4 space-y-4">
      <p>
        {data.meta.description}
      </p>
      <p>
        <svelte:component this={data.content} />
      </p>
    </article>
    <div class="mt-4 flex justify-evenly">
      {#each data.meta.categories as category}
        <span class="chip variant-filled cursor-default">{category}</span>
      {/each}
    </div>
  </div>
  <hr class="opacity-70" />
  <footer class="card-footer px-4">
    <small>on {formatDate(data.meta.date)}</small>
  </footer>
</div>
