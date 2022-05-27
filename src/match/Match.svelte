<script>
  import Status from './Status.svelte';
  import Result from './Result.svelte';
  import Teams from './Teams.svelte';
  export let match;
</script>

<div class="match">
  <div class="match-container">
    <div class="status">
      <Status statusText={match.status} />
    </div>
    <Result {match} />
    <Teams {match} />
    <!--   <Channel {match} {dimensions} /> -->
  </div>
</div>

<style>
  .match {
    width: 100%;
  }

  .match-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .status {
    width: 35px;
  }
</style>
