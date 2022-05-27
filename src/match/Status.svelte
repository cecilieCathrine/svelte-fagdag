<script>
  export let statusText = '';

  let status;
  $: status = sportStatus[statusText];

  export const sportStatus = Object.freeze({
    CANCELLED: 'Avlyst',
    INTERRUPTED: 'Avbrutt',
    DELETED: 'Slettet',
    UNKNOWN: 'Ukjent',
    POSTPONED: 'Utsatt',
    ABANDONED: 'Avbrutt',
    FINISHED: 'Slutt',
    NOT_STARTED: 'Ikke startet',
    PAUSE: 'Pause',
    STARTED: 'Pågår',
  });
</script>

<span class="content text">{status}</span>

<style>
  .content {
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: rgba(#100811, 70%);
  }

  .content.text {
    white-space: nowrap;
  }
</style>
