<script lang="ts">
  import Progress from './Progress.svelte'
  import Step from './Step.svelte'
  const steps = [
    {
      text: '1'
    },
    {
      text: '2'
    },
    {
      text: '3'
    },
    {
      text: '4'
    },
    {
      text: '5'
    },
    {
      text: '6'
    },
  ]
  let currentStep = 1
  let width = '0'

  const prevStep = () => {
    if (currentStep !== 1) {
      currentStep--
      width = (currentStep - 1) / (steps.length - 1) * 100 + '%'
    }
  }
  const nextStep = () => {
    if (currentStep !== steps.length) {
      currentStep++
      width = (currentStep - 1) / (steps.length - 1) * 100 + '%'
    }
  }
</script>

<div class="container">
  <div class="progress-container">
    <Progress --width={width} />
    {#each steps as step}
      <Step text={step.text} {currentStep} />
    {/each}
  </div>

  <button class="btn" id="prev" disabled={currentStep === 1} on:click={prevStep}>Prev</button>
  <button class="btn" id="next" disabled={currentStep === steps.length} on:click={nextStep}>Next</button>
</div>

<style>
  @import url('https://fonts.googleapis.com/css?family=Muli&display=swap');

  :root {
    --line-border-fill: #3498db;
    --line-border-empty: #e0e0e0;
  }

  .container {
    text-align: center;
    margin: 100px auto;
  }

  .progress-container {
    display: flex;
    justify-content: space-between;
    position: relative;
    margin-bottom: 30px;
    max-width: 100%;
    width: 600px;
  }

  .progress-container::before {
    content: '';
    background-color: var(--line-border-empty);
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
    height: 4px;
    width: 100%;
    z-index: -1;
  }

  .btn {
    background-color: var(--line-border-fill);
    color: #fff;
    border: 0;
    border-radius: 6px;
    cursor: pointer;
    font-family: inherit;
    padding: 8px 30px;
    margin: 5px;
    font-size: 14px;
  }

  .btn:active {
    transform: scale(0.98);
  }

  .btn:focus {
    outline: 0;
  }

  .btn:disabled {
    background-color: var(--line-border-empty);
    cursor: not-allowed;
  }
</style>