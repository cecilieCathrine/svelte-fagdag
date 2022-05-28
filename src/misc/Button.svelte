<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();
</script>

<button class="btn-new" on:click={() => dispatch('new')}>Ny turnering</button>

<style>
  .btn-new {
    border-radius: 40px;
    padding: 10px 1rem;
    background: #ffffff;
    border: 2px solid #ffbf94;
    cursor: pointer;
    font-weight: 600;
  }
</style>
