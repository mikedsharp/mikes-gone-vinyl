<script lang="ts">
  import VinylRecord from "./lib/VinylRecord.svelte";
</script>

<main>
  <div class="banner">
    <h1>Mike's record collection</h1>
  </div>
  <div class="record-grid">
    <VinylRecord
      cover={"/sleeves/black-sabbath-master-of-reality-sleeve.png"}
      disc={"/sleeves/black-sabbath-master-of-reality-disc.png"}
    />
    <VinylRecord
      cover={"/sleeves/pearl-jam-chicago-sleeve.png"}
      disc={"/sleeves/pearl-jam-chicago-disc.png"}
    />
  </div>
</main>

<style lang="scss">
  @import url("./assets/fonts/fonts.scss");

  :global(body) {
    margin: 0;
  }

  :global(#app) {
    background-image: url("./assets/textures/wood-background.jpg");
    background-size: cover;
    height: 100vh;
    width: 100vw;
    overflow: hidden;
  }

  main {
    height: 100%;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
  }
  h1 {
    font-family: "myUnderwood", Arial, Helvetica, sans-serif;
    color: white;
    color: #e64741;
    text-shadow: 2px 2px #eee;
    text-align: center;
    font-size: 5rem;
    flex: 1;
    margin: 0;
  }
  .banner {
    flex: 0;
  }
  .record-grid {
    padding: 30px;
    margin-top: 20px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    flex: 1;
    overflow: auto;
  }
</style>
