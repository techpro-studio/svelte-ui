<script>
  export let icon;
</script>

<style>
  .button{
    display: inline-block;
    vertical-align: middle;
    user-select: none;
    padding: 5px;
    background-color: transparent;
    border: 1px solid transparent;
    outline: 0;
    cursor: pointer;
    transition: all .3s ease;
  }
  .center {
    display: block;
    margin-left: auto;
    margin-right: auto;
    width: 12px;
    height: 12px;
  }
</style>

<button on:click type="button" class="button">
  <img class="center" src={icon} alt="icon">
</button>
