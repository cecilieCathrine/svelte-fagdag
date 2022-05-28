<script>
  import Status from './Status.svelte';
  import Result from './Result.svelte';
  import Teams from './Teams.svelte';
  export let match;
</script>

<div class="match">
  <div class="match-container">
    <div class="flex">
      <Status statusText={match.status} />
      <Result {match} />
      <Teams {match} />
    </div>
    <span class="text bold">{match.programs[0]?.channelName || ''}</span>
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
  .flex {
    display: flex;
    gap: 0.5rem;
    align-items: center;
  }
</style>
