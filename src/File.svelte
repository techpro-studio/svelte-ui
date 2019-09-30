<script>
  import IconButton from "./IconButton.svelte";

  export let name;
  export let size;
  export let progress;
  export let id;

  import { createEventDispatcher } from 'svelte'
  const dispatch = createEventDispatcher();

  function onCloseClick() {
    dispatch('close_click', id);
  }

</script>

<style>
  .file {
    position: relative;
    margin-bottom: 20px;
  }

  .file:first-child {
    margin-top: 30px;
  }

  .progress-bar {
    height: 42px;
    overflow: hidden;
    background-color: #f7f7f7;
    border-radius: 15px;
  }

  .uploaded {
    height: 42px;
    background-color: #eee;
  }

  .info {
    display: flex;
    align-items: center;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 42px;
    padding-left: 30px;
  }

  .name {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .size {
    white-space: nowrap;
  }

  .right {
    display: flex;
    align-items: center;
    margin-left: auto;
    padding-left: 30px;
    padding-right: 10px;
  }

  .size {
    margin-right: 20px;
  }

  .action {

  }
</style>

<div class="file">
  <div class="progress-bar">
    <div class="uploaded" style="width: {progress}%"></div>
  </div>
  <div class="info">
    <div class="name">{name}</div>
    <div class="right">
      <div class="size">{size}</div>
      <div class="action">
        <IconButton icon="/icons/close.svg" on:click={onCloseClick} />
      </div>
    </div>
  </div>
</div>
