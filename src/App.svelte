<script>
  import { onMount } from 'svelte';
  import Tournament from './tournament/Tournament.svelte';
  import * as data from './json/data.json';
  import { selectedTournament } from './store/tournament';
  import Button from './misc/Button.svelte';

  let tournaments = [];

  onMount(() => {
    tournaments = data.tournaments;
    $selectedTournament = tournaments[Math.floor(Math.random() * tournaments.length)];
  });

  const newTournament = () => {
    $selectedTournament = tournaments[Math.floor(Math.random() * tournaments.length)];
  };
</script>

<main>
  <div class="tournament-container">
    {#if $selectedTournament}
      <Tournament tournament={$selectedTournament} />
    {/if}
  </div>
  <Button on:new={newTournament} />
</main>

<style>
  main {
    text-align: center;
    max-width: 300px;
    margin: 0 auto;
  }
  .tournament-container {
    margin: 2rem 0;
    background-color: #f4f4f4;
    padding: 1em;
  }
</style>
