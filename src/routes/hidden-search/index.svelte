<script lang="ts">
  let showSearch: boolean = false
</script>

<div class="search" class:active={showSearch}>
  <input type="text" class="input" placeholder="Search...">
  <button class="btn" on:click={() => showSearch = true}>
    <i class="fas fa-search"></i>
  </button>
</div>

<style>
  .search {
    position: relative;
  }

  .search .input {
    background-color: #fff;
    border: 0;
    font-size: 17px;
    padding: 15px;
    width: 50px;
    transition: width 0.3s ease;
  }

  .btn {
    background-color: #fff;
    border: 0;
    cursor: pointer;
    font-size: 20px;
    position: absolute;
    top: 0;
    left: 0;
    height: 50px;
    width: 50px;
    transition: transform 0.3s ease;
  }

  .btn:focus,
  .input:focus {
    outline: none;
  }

  .active .input {
    width: 200px;
  }

  .active .btn {
    transform: translateX(198px);
  }
</style>