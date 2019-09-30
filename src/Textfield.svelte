<script>
  export let id;
  export let label;
  export let value;
  export let error;

  $: hasError = error !== null && error !== undefined;
  $: labelClass = `form-label ${hasError ? 'error': ''}`;
  $: inputClass = `form-input ${hasError ? 'form-error': ''}`;

</script>

<style>
  .form-field {
    display: flex;
    flex-direction: column;
    position: relative;
    padding-bottom:20px;
  }

  .form-label {
    margin-bottom: 5px;
  }

  .form-input {
    height: 50px;
    padding: 0 25px;
    background-color: #eee;
    border: 1px solid #eee;
    border-radius: 25px;
    font-size: 16px;
  }

  .form-error {
    border-color: #dd5234;
  }

  .error {
    color: #dd5234;
  }

  .error-label {
    position: absolute;
    left: 0;
    bottom: 0;
    color: #dd5234;
    font-size: 10px;
    line-height: 15px;
  }
  @media (max-width: 360px) {
    .error-label{
      font-size: 8px;
    }
  }


</style>

<div class="form-field">
  <label class={labelClass} for={id}>{label}</label>
    <input type="text"
          bind:value={value}
          id={id}
          class={inputClass}
    >
    {#if hasError}
      <div class="error-label">{error}</div>
    {/if}
</div>
