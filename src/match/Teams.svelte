<script>
  export let match;
</script>

<div class="teams">
  <span class="team">{match.participants[0].participant.name}</span>
  <span class="team">{match.participants[1].participant.name}</span>
</div>

<style>
  .teams {
    display: flex;
    flex-direction: column;
    flex: 1;
    font-size: 14px;
    overflow: hidden;
  }

  .team {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
</style>
