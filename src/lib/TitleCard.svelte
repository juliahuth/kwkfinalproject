<script>
  let { title, subtitle } = $props();
</script>

<div class="title-card">
  <div class="content">
    <h1>{title}</h1>
    <p>{subtitle}</p>
  </div>
</div>

<style>
  .title-card {
    background-color: #030c26; /* deeper navy */
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 1.5rem;
    box-sizing: border-box;
    font-family: 'Impact', 'Segoe UI', sans-serif;
  }

  .content {
    max-width: 600px;
    background-color: #f1f5ff; /* very pale blue */
    padding: 1.5rem 2rem;
    border: 4px solid #0a1a40; /* dark navy border */
    border-radius: 1rem;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.4);
  }

  h1 {
    font-size: 3.2rem;
    color: #0a1a40;
    margin: 0 0 0.5rem 0;
    letter-spacing: 1.5px;
    text-transform: uppercase;
  }

  p {
    font-size: 1.2rem;
    color: #1b1b1b;
    margin: 0.5rem 0 0 0;
    font-family: 'Georgia', serif;
    line-height: 1.4;
  }

  @media (max-width: 600px) {
    .content {
      padding: 1.2rem 1.5rem;
    }

    h1 {
      font-size: 2.4rem;
    }

    p {
      font-size: 1rem;
    }
  }
</style>
