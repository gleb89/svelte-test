<script>
    let count = 0;
    let name = 'world';
    $: doubled = count * 2;
    function handleClick() {
      count += 1;
    }
    $: if (count) {
    console.log('watch',count);
}
  </script>
  {name}
  <input bind:value={name}>
  <button on:click="{handleClick}">Click me!</button>
  
  <p>{count} doubled is {doubled}</p>