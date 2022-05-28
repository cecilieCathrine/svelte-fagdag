<div class="list-item">
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
    background-color: #fafafa;
  }

  .list-item:nth-of-type(2n) {
    background-color: white;
  }
</style>
