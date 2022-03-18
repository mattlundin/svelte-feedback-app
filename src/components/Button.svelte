<script>
  export let style = 'primary'
  export let type = 'button'
  export let disabled = 'false'
</script>

<button {type} {disabled} class={style}>
  <slot></slot>
</button>

<style>
  button {
    height: 40px;
    width: 100px;
    color: #fff;
    border: 0;
    border-radius: 8px;
    cursor: pointer;
  }

  .primary {
    background-color: #202142;
  }

  .secondary {
    background: #ff6a95;
  }

  button:hover {
    transform: scale(0.98);
    opacity: 0.9;
  }

  button:disabled {
    background: #cccccc;
    color: #333;
    cursor: auto;
  }

  button:disabled:hover {
    transform: scale(1);
    opacity: 1;
  }

</style>