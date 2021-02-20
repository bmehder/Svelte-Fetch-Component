<script>
  export let message = "something went wrong.";
  console.log(message);
</script>

<article>
  <h1>Don't panic ...<br /><span>💩</span><br />but {message}</h1>
</article>

<style>
  article {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    text-align: center;
  }
  span {
    font-size: 5em;
  }
</style>
