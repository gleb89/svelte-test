<script>
  // populated with data from the endpoint
  let item = "about";
  let parcels = [1, 2, 3, 4];
  const OnPkGet = (pk) => {
    console.log(pk);
    parcels = parcels.filter(el=>{
        return el != pk
    })
  };
  import { onMount } from "svelte";
  const endpoint = "https://jsonplaceholder.typicode.com/posts";
  let posts = [];

//   onMount(async function () {
//     const response = await fetch(endpoint);
//     const data = await response.json();
//     console.log(data);
//   });

  import axios from "axios";
  onMount(async function () {
  const response = await axios.get(endpoint);
  console.log(response.data);
  posts = response.data;
});
</script>

<svelte:head>
  <title>about</title>
</svelte:head>

<section>
  <h1>{item}</h1>
  {#each posts as parcel}
    <p on:click={() => OnPkGet(parcel)}>{parcel.title}</p>
  {/each}
</section>

<a href="/">home</a>
