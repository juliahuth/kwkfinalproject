<script>
  let { children } = $props();
</script>

<div class="article-text">
  <p>{@render children()}</p>
</div>

<style>
  .article-text {
    margin: 30vh auto;
    width: 60%;
    background-color: #f9fbff; /* soft cool tone */
    color: #08122e; /* bold navy */
    border: 3px solid #0a1a40; /* rich navy accent */
    border-radius: 0.75rem;
    padding: 1.75rem 2rem;
    box-shadow: 0 6px 20px rgba(10, 26, 64, 0.18);
    font-family: 'Georgia', serif;
    line-height: 1.5;
    text-align: left;
    transition: box-shadow 0.3s ease;
  }

  .article-text:hover {
    box-shadow: 0 10px 30px rgba(10, 26, 64, 0.25);
  }

  p {
    margin: 0;
    font-size: 1.2rem;
    font-weight: 500;
    letter-spacing: 0.2px;
  }

  @media (max-width: 768px) {
    .article-text {
      width: 90%;
      padding: 1.25rem 1.5rem;
      margin: 20vh auto;
    }

    p {
      font-size: 1rem;
    }
  }
</style>
