<script lang="ts">
  import Panel from './Panel.svelte'
  const panels = [
    {
      text: 'Explore The World',
      imgUrl: 'https://images.unsplash.com/photo-1558979158-65a1eaa08691?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80'
    },
    {
      text: 'Wild Forest',
      imgUrl: 'https://images.unsplash.com/photo-1572276596237-5db2c3e16c5d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80'
    },
    {
      text: 'Sunny Beach',
      imgUrl: 'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1353&q=80'
    },
    {
      text: 'City on Winter',
      imgUrl: 'https://images.unsplash.com/photo-1551009175-8a68da93d5f9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1351&q=80'
    },
    {
      text: 'Mountains - Clouds',
      imgUrl: 'https://images.unsplash.com/photo-1549880338-65ddcdfd017b?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80'
    },
  ]
</script>

<div class="container">
  {#each panels as panel}
    <Panel text={panel.text} imgUrl={panel.imgUrl} />
  {/each}
</div>

<style>
  @import url('https://fonts.googleapis.com/css?family=Muli&display=swap');

  .container {
    display: flex;
    width: 100%;
    margin: 0 auto;
  }

  @media (max-width: 480px) {
    .container {
      width: 100vw;
    }
  }
</style>