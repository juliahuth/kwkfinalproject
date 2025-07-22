<script>
  // `layout` can be either "right" or "left"
  let { layout, sticky, scrolly } = $props(); 
</script>

<div class="wrapper {layout}">
  <div class="sticky">
    {@render sticky()}
  </div>

  <div class="scrolly">
    {@render scrolly()}
  </div>
</div>

<style>
  .wrapper {
    background-color: #0a1a40; /* rich navy background */
    padding: min(100vh, 24rem) 1rem;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-items: flex-start;
    font-family: 'Georgia', serif;
    color: #ffffff;
    border-top: 6px solid #12264c;
    border-bottom: 6px solid #12264c;
    gap: 1rem;
  }

  .left .scrolly {
    order: 0;
  }

  .left .sticky {
    order: 1;
  }

  .right .scrolly {
    order: 1;
  }

  .right .sticky {
    order: 0;
  }

  .sticky,
  .scrolly {
    flex: 1 1;
    padding: 0.75rem;
  }

  .sticky {
    position: sticky;
    top: 50vh;
    transform: translateY(-50%);
    background-color: #ffffff;
    color: #0a1a40;
    padding: 2rem 1.5rem;
    border-radius: 1rem;
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.2);
    z-index: 0;
    max-width: 500px;
    margin-inline: auto;
  }

  .scrolly {
    z-index: 1;
    color: #e2e6f0;
    font-size: 1.1rem;
    line-height: 1.6;
    max-width: 650px;
  }

  @media (max-width: 768px) {
    .wrapper {
      flex-direction: column;
      padding: 2rem 1rem;
      width: 100%;
    }

    .sticky,
    .scrolly {
      flex: 1 1 auto;
      min-width: 100%;
      position: static;
      transform: none;
      padding: 1rem 0;
    }

    .sticky {
      margin-bottom: 1.5rem;
    }
  }
</style>
