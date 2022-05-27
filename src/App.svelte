<script>
  import { onMount } from 'svelte';
  import Tournament from './tournament/Tournament.svelte';
  import * as data from './json/data.json';

  let tournaments = [];

  onMount(() => {
    tournaments = data.tournaments;
    console.log(tournaments);
  });
</script>

<main>
  {#each tournaments as tournament}
    <Tournament {tournament} />
  {/each}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 300px;
    margin: 0 auto;
    background-color: #f4f4f4;
  }
</style>
