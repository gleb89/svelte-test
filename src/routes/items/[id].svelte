<script context="module">
  import { page } from "$app/stores";

  export async function load(ctx) {
    const url = `https://jsonplaceholder.typicode.com/posts/${ctx.params.id}`;
    const res = await fetch(url);
    const post = await res.json();
    return { props: { post } };
  }
</script>

<!-- component -->
<script>
  export let post;
</script>

<svelte:head>
  <title>post</title>
</svelte:head>



<p>{post.id}</p>
<p>{post.title}</p>
