<script>
  import Backdrop from "../lib/Backdrop.svelte";
  import Card from "../lib/Card.svelte";
  import Timeline from "../lib/Timeline.svelte";
</script>

<svelte:head>
  <title>Anna és Marca esküvője</title>
</svelte:head>

<Backdrop img="background" />
<Card>
  <div id="title-container">
    <h1>Anna és Marca</h1>
    <img src="/img/bajusz.png" alt="dekor" />
  </div>
  <main>
    📅 2023. június 10.<br />
    📍Megyer
  </main>
  <Timeline />
</Card>

<style>
  #title-container {
    text-align: center;
    font-size: 40px;
  }

  h1 {
    margin-bottom: 0;
  }

  img {
    width: 300px;
    margin-bottom: 3rem;
  }

  main {
    text-align: center;
    display: flex;
    justify-content: center;
    font-size: 2rem;
    line-height: 2.8rem;
  }

  @media (max-aspect-ratio: 1/1) {
    h1 {
      font-size: 2ch;
    }

    main {
      font-size: 1.6rem;
      line-height: 2rem;
    }
  }
</style>
