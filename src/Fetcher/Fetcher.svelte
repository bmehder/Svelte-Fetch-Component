<script>
  import { fade } from "svelte/transition";
  import Error from "./Error.svelte";
  import Spinner from "./Spinner.svelte";

  export let endpoint = "https://jsonplaceholder.typicode.com/users";

  async function getData(url) {
    const response = await fetch(url);
    const data = await response.json();
    return data;
  }

  let response = getData(endpoint);
  $: console.log(response);
</script>

{#await response}
  <Spinner size="168" speed="750" color="#307ad5" thickness="3" gap="42" />
{:then data}
  <div in:fade>
    {JSON.stringify(data)}
  </div>
{:catch}
  <Error />
{/await}
