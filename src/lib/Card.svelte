<div id="card">
  <div id="card-inner">
    <slot />
  </div>
</div>

<style>
  #card {
    --padding: 6px;
    --border-radius: 10px;

    position: absolute;
    top: 0;
    right: 0;
    margin: 3rem;
    width: 50%;
    height: calc(100% - 6rem);
    background-color: rgba(252, 247, 240, 0.88);
    padding: var(--padding);
    display: flex;
    align-items: stretch;
    border-radius: var(--border-radius);
  }

  #card-inner {
    position: absolute;
    width: calc(100% - 2 * var(--padding));
    height: calc(100% - 2 * var(--padding));
    border-radius: var(--border-radius);
  }

  @media (max-aspect-ratio: 1/1) {
    #card {
      top: 50%;
      left: 0;
      right: 0;
      width: 80%;
      height: 55%;
      margin-inline: auto;
    }
  }
</style>
