<script>
  export let value = 0;
  export let label = "";
  export let min = 0;
  export let max = 100;
  export let id;
  export let step = 1;

  $: percent = (value / max) * 100;
  $: style = `background: linear-gradient(to right, #dd5234 0%, #dd5234 ${percent}%, #e1e1e1 ${percent}%, #e1e1e1 100%)`;
</script>

<style>
  .slider-field {
    display: flex;
    flex-direction: column;
    position: relative;
    padding-bottom: 20px;
  }

  .slider-label {
    margin-bottom: 15px;
    line-height: 28px;
  }



input {
  -webkit-appearance: none;
  @apply bg-primary-50 w-full rounded cursor-pointer;
  width: 100%;
  height: 4px;
}
input:disabled {
  @apply bg-gray-300;
}
input::range-thumb {
  -webkit-appearance: none;
  /*@apply rounded-full p-1 w-5 h-5 elevation-3 bg-primary-500;*/
  background-color: red;
}

input::-ms-thumb {
  margin: 0;
}
input:focus {
  outline: none;
}
input:focus::range-thumb {
  -webkit-appearance: none;
  /*@apply rounded-full p-1 w-5 h-5 elevation-3 bg-primary-500;*/
  margin-top: -0.5rem;
}
input:focus::range-track {
  @apply rounded;
  height: 4px;
}


  input[type=range]::-webkit-slider-thumb {
    width: 20px;
    height: 20px;
    background-color: #fff;
    border: 2px solid #dd5234;
    border-radius: 50%;
    box-shadow: 0 2px 4px #cdcdcd;
    cursor: pointer;
    -webkit-appearance: none;
  }

  input[type=range]::-moz-range-thumb {
    width: 20px;
    height: 20px;
    background-color: #fff;
    border: 2px solid #dd5234;
    border-radius: 50%;
    box-shadow: 0 2px 4px #cdcdcd;
    cursor: pointer;
  }

  input[type=range]::-moz-focus-outer {
    border: 0;
  }

  input[type=range]::-ms-thumb {
    width: 20px;
    height: 20px;
    background-color: #fff;
    border: 2px solid #dd5234;
    border-radius: 50%;
    box-shadow: 0 2px 4px #cdcdcd;
    cursor: pointer;
  }

  .slider-panel {
    position: relative;
    z-index: -1;
  }

  .slider-panel::before,
  .slider-panel::after {
    display: block;
    content: "";
    position: absolute;
    top: -10px;
    width: 12px;
    height: 12px;
    border-radius: 50%;
  }

  .slider-panel::before {
    left: 2px;
    background-color: #dd5234;
  }

  .slider-panel::after {
    right: -2px;
    background-color: #e1e1e1;
  }
</style>

<div class="slider-field">
  <label class="slider-label">{@html label}</label>
  <input
    type="range"
    {min}
    {max}
    {step}
    bind:value
    on:change
    style={style}
  >
  <div class="slider-panel"></div>
</div>
