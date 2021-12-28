<script lang="ts">
  export let text: String = ''
  export let imgUrl: String = ''
  let isActive: Boolean = false
  console.log('Hello Panel')
</script>

<div class="panel" class:active={isActive} style="background-image: url({imgUrl})" on:click={() => isActive = !isActive}>
  <h3>{text}</h3>
</div>

<style>
  .panel {
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    height: 80vh;
    border-radius: 50px;
    color: #fff;
    cursor: pointer;
    flex: 0.5;
    margin: 10px;
    position: relative;
    -webkit-transition: all 700ms ease-in;
  }

  .panel h3 {
    font-size: 24px;
    position: absolute;
    bottom: 20px;
    left: 20px;
    margin: 0;
    opacity: 0;
  }

  .active {
    flex: 5;
  }

  .active h3 {
    opacity: 1;
    transition: opacity 0.3s ease-in 0.4s;
  }
</style>