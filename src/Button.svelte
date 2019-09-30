<script>
  export let link;
  export let theme = '';

  $: cssClass = `button-link ${theme}`;
</script>

<style>
  .button-link {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    padding: 0 20px;
    border-radius: 25px;
    border: 1px solid transparent;
    color: #dd5234;
    font-weight: 500;
    line-height: 20px;
    text-decoration: none;
    cursor:pointer;
    transition: all .3s ease;
  }

  .solid {
    background-color: #dd5234;
    color: #fff;
  }

  .solid:hover {
    background-color: #fa6f51;
  }

  .outlined {
    border-color: #dd5234;
  }

  .outlined:hover {
    background-color: #dd5234;
    color: #fff;
  }

  @media (max-width: 767px) {
    .button-link {
      min-width: 200px;
      height: 44px;
      font-size: 14px;
    }
  }

  @media (min-width: 768px) {
    .button-link {
      min-width: 220px;
      height: 50px;
      font-size: 16px;
    }
  }
</style>

<a on:click type="submit" href={link} class={cssClass}><slot></slot></a>
