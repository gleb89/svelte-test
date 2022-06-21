<!-- <svelte:head>
  <title>Welcome</title>
</svelte:head>

<h1>Hello and welcome to my site!</h1>

<a href="/about">About my site</a> -->


<!-- preloader -->

<script context="module">
    export async function load() {
        const url = `https://jsonplaceholder.typicode.com/posts`;
        const res = await fetch(url);
        const posts = await res.json();
        return {props: {posts}}
    }
</script>



<svelte:head>
    <title>About</title>
</svelte:head>

<!-- component -->
<script>
    export let posts; 
    const OnPkGet = (pk) => {
    console.log(pk);
  };
</script>

{#each posts as post}
<p></p>
<a href="/items/{post.id}">{post.title}</a>
{/each}