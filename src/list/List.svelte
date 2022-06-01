<div class="list">
  <header class="list-header">
    <slot name="header" />
  </header>
  <slot name="content" />
</div>

<style>
  .list {
    display: flex;
    flex-direction: column;
    border-radius: 12px;
    overflow: hidden;
    background-color: white;
  }
  .list-header {
    height: 56px;
    min-height: 56px;
    display: flex;
    align-items: center;
    padding: 0 15px;
    background-color: white;
  }
</style>
