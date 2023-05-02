<script>
  export let data;

  const formatDate = (dt) => {
    const fmt = new Intl.DateTimeFormat("en", { dateStyle: "medium" });
    return fmt.format(new Date(dt));
  };
</script>

<svelte:head>
  <title>Hello</title>
</svelte:head>

<div class="mt-4 container mx-auto flex flex-col space-y-4">
  {#each data.posts as post}
    <div class="card p-4">
      <header class="card-header p-4">
        <h3><a href={post.slug}>{post.title}</a></h3>
      </header>
      <div class="p-4 space-y-4">
        <article>
          <p>
            {post.description}
          </p>
        </article>
      </div>
      <hr class="opacity-50" />
      <footer class="card-footer p-4">
        <small>on {formatDate(post.date)}</small>
      </footer>
    </div>
  {/each}
</div>
