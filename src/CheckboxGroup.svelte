<script>
  export let label;
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

  .form-tags {
    display: flex;
    flex-wrap: wrap;
    margin: 0 -5px -20px;
  }
</style>

<div class="form-field">
  <label class="form-label">{label}</label>
  <div class="form-tags">
    <slot></slot>
  </div>
</div>
