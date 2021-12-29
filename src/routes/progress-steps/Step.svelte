<script lang="ts">
  export let text: string = ''
  export let currentStep: number = 0
</script>

<div class="circle" class:active={currentStep >= parseInt(text, 10)}>{text}</div>

<style>
  .circle {
    background-color: #fff;
    color: #999;
    border-radius: 50%;
    height: 30px;
    width: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 3px solid #e0e0e0;;
    transition: 0.4s ease;
  }

  .active {
    border-color: #3498db;
  }
</style>