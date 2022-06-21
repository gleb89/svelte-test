<script>
    import Button, { Label } from '@smui/button';
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
  
  <Button on:click="{handleClick}" touch  variant="outlined">
    <Label>clicked</Label>
  </Button>
  
  <p>{count} doubled is {doubled}</p>