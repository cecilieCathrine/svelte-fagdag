<script>
  import List from '../list/List.svelte';
  import ListItem from '../list/ListItem.svelte';
  import Match from '../match/Match.svelte';
  import Logo from '../misc/Logo.svelte';
  import { fade } from 'svelte/transition';
  export let tournament;
</script>

{#key tournament}
  <div class="tournament" in:fade={{ duration: 300, delay: 100 }}>
    <List>
      <svelte:fragment slot="header">
        <div class="header-container flex">
          <div class="button-content-right">
            <Logo {tournament} position="center left" width="24px" />
            <span class="button-text">{tournament.name}</span>
          </div>
        </div>
      </svelte:fragment>
      <svelte:fragment slot="content">
        {#each tournament.events as match}
          <ListItem>
            <Match {match} />
          </ListItem>
        {/each}
      </svelte:fragment>
    </List>
  </div>
{/key}

<style>
  .tournament:not(:last-child) {
    margin-bottom: 8px;
  }

  .header-container {
    width: 100%;
    display: flex;
  }

  .button-content-right {
    display: flex;
    align-items: center;
    min-width: 0;
    height: 40px;
    max-height: 40px;
    padding: 0 11px;
    border-radius: 100px;
    background-color: rgba(16, 1, 24, 0.05);
  }

  .button-text {
    font-size: 14px;
    line-height: 16px;
    font-weight: 600;
    margin-right: 12px;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
</style>
