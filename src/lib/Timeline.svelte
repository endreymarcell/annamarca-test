<script lang="ts">
  function msToDays(ms: number) {
    return Math.round(ms / 1000 / 60 / 60 / 24);
  }
  const startDate = new Date("2022-08-07");
  const goalDate = new Date("2023-06-10");
  const fullDiffMs = goalDate - startDate;
  const fullDiffDays = msToDays(fullDiffMs);

  const currentDate = new Date();
  const currentDiffMs = goalDate - currentDate;
  const currentDiffDays = msToDays(currentDiffMs);

  const progress = (fullDiffDays - currentDiffDays) / fullDiffDays;
</script>

<div id="timeline">
  <div id="marker" style={`--progress: ${progress};`}>
    <div id="past" />
    <img src="/img/couple.png" alt="marker ikon" />
    <div id="future" />
  </div>
  <div id="line" />
  <div id="dates">
    <div>2022. augusztus 7.<br />Eljegyzés</div>
    <div>Már csak {currentDiffDays} nap van hátra!</div>
    <div>2023. június 10.<br />Esküvő</div>
  </div>
</div>

<style>
  #timeline {
    position: absolute;
    bottom: 0;
    width: 100%;
  }

  #marker {
    display: flex;
    align-items: end;
    --img-width: 70px;
    --progress: 0.5;
  }

  #marker #past {
    width: calc((100% - var(--img-width)) * var(--progress));
  }

  #marker img {
    width: var(--img-width);
  }

  #line {
    width: 100%;
    height: 5px;
    background: linear-gradient(to right, transparent, maroon);
  }

  #dates {
    display: flex;
    justify-content: space-between;
  }

  #dates > div {
    margin-inline: 1rem;
    margin-block: 0.4rem;
  }

  #dates > div:last-child {
    text-align: end;
  }
</style>
