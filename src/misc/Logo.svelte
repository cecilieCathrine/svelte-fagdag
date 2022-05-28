<script>
  export let tournament;
  export let position;
  export let width;
</script>

{#if tournament.country && tournament.country.images.length}
  <img
    src={tournament.country.images[0].url}
    alt={tournament.name}
    style={`background-position:${position}; width: ${width}`}
    class="margin-right"
  />
{/if}

<style>
  .margin-right {
    margin-right: 8px;
  }
</style>
