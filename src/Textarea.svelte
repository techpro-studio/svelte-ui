<script>
  export let id;
  export let label;
  export let error;
  export let value;
  export let resizable = false;

  $: hasError = error !== null && error !== undefined;
  $: labelClass = `form-label ${hasError ? 'error': ''}`;
  $: inputClass = `form-textarea ${resizable ? '' : 'not-resizable'}  ${hasError ? 'form-error': ''}`;
  
</script>

<style>
  .form-field {
    display: flex;
    flex-direction: column;
    position: relative;
    padding-bottom: 20px;
  }

  .form-label {
    margin-bottom: 5px;
  }

  .form-textarea {
    height: 150px;
    padding: 25px;
    background-color: #eee;
    border: 1px solid #eee;
    border-radius: 15px;
    font-size: 16px;
  }

  .not-resizable {
    resize: none
  }

  .form-error{
    border-color: #dd5234;
  }

  .error {
    opacity: 1;
    color: #dd5234;
  }

  .form-error-value {
    position: absolute;
    left: 0;
    bottom: 0;
    color: #dd5234;
    font-size: 10px;
    line-height: 15px;
  }
</style>

<div class="form-field">
  <label class={labelClass} for={id}>{label}</label>
  <textarea id={id}
            bind:value={value}
            class={inputClass}
  ></textarea>
  {#if hasError}
    <div class="form-error-value">{error}</div>
  {/if}
</div>
