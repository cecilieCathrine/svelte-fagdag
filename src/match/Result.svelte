<script>
  export let match;

  let homeScore;
  let awayScore;

  $: homeScore = match.participants[0].results.find(res => res.resultType === 'RUNNING_SCORE');
  $: awayScore = match.participants[1].results.find(res => res.resultType === 'RUNNING_SCORE');
</script>

<div
  class="result flex-column-center"
  class:end-result={match.status === 'FINISHED'}
  class:on-going={match.status === 'IN_PROGRESS'}
>
  {#if match.status === 'NOT_STARTED'}
    <span>-</span>
  {:else}
    <div>{homeScore?.value || 0}</div>
    <div>{awayScore?.value || 0}</div>
  {/if}
</div>

<style>
  .result {
    background-color: #ededed;
    font-weight: bold;
    font-size: 14px;
    line-height: 120%;
    width: 28px;
    min-width: 28px;
    height: 48px;
    border-radius: 16px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .result.on-going {
    background-color: #212dff;
    color: #ffffff;
  }

  .result.end-result {
    background-color: #100118;
    color: #ffffff;
  }
</style>
