<script lang="ts">
  const scale = (num, in_min, in_max, out_min, out_max) => {
    return ((num - in_min) * (out_max - out_min)) / (in_max - in_min) + out_min
  }
  const blurring = () => {
    load++

    if (load > 99) {
      clearInterval()
    }

    opacity = scale(load, 0, 100, 1, 0)
    filter = `blur(${scale(load, 0, 100, 30, 0)}px)`
  }

  let opacity
  let filter
  let bg
  let load = 0
  let int = setInterval(blurring, 30)
</script>

<section class="bg" style="filter: {filter}"></section>
<div class="loading-text" style="opacity: {opacity}">{load}%</div>

<style>
  .bg {
    background: url('https://images.unsplash.com/photo-1576161787924-01bb08dad4a4?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2104&q=80')
      no-repeat center center/cover;
    position: absolute;
    top: -30px;
    left: -30px;
    width: calc(100vw + 60px);
    height: calc(100vh + 60px);
    z-index: -1;
    filter: blur(0px);
  }

  .loading-text {
    font-size: 50px;
    color: #fff;
  }
</style>