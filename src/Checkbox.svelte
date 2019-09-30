<script>
  export let name;
  export let checked = false;
</script>

<style>
  .form-tag {
    padding: 5px;
  }

  .form-tag__label {
    display: inline-block;
    height: 40px;
    padding: 0 25px;
    background-color: #fff;
    border: 1px solid #1e212a;
    border-radius: 40px;
    color: #1e212a;
    font-size: 12px;
    line-height: 40px;
    cursor: pointer;
    transition: all .3s ease;
  }

  /*.form-tag__label:hover,*/
  .form-tag--checked .form-tag__label {
    color: #fff;
    background: #1e212a;
  }

  .form-tag__input {
    position: absolute;
    opacity: 0;
    pointer-events: none;
  }
</style>

<div class="form-tag" class:form-tag--checked={checked}>
  <label class="form-tag__label">
    <input type="checkbox"
           class="form-tag__input"
           name="services"
           id="services"
           bind:checked={checked}
    >{name}
    </label>
</div>
