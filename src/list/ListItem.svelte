<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();
</script>

<div class="list-item" on:click={() => dispatch('listItemClick')}>
  <slot />
</div>

<style>
  .list-item {
    min-height: 56px;
    display: flex;
    align-items: center;
    padding: 4px 10px;
  }

  .list-item:nth-of-type(2n-1) {
    background-color: white;
  }

  .list-item:nth-of-type(2n) {
    background-color: #fafafa;
  }
</style>
