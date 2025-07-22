<script>
  import { onMount, onDestroy } from "svelte";

  let { children, callback, options } = $props();
  let uniqueId = `article-${crypto.randomUUID()}`;
  let observer;

  onMount(() => {
    const observedElement = document.getElementById(uniqueId);
    observer = new IntersectionObserver(callback, options);
    if (observedElement) observer.observe(observedElement);
  });

  onDestroy(() => {
    observer?.disconnect();
  });
</script>

<div id={uniqueId} class="article-text">
  <p>{@render children()}</p>
</div>

<style>
  .article-text {
    margin: 40vh auto;
    width: 60%;
    background-color: #f0f4ff; /* soft blue-tinted background */
    color: #08122e; /* darker navy text */
    border: 3px solid #0a1a40; /* strong navy border */
    border-radius: 1rem;
    padding: 1.75rem 2rem;
    box-shadow: 0 6px 20px rgba(10, 26, 64, 0.2);
    font-family: 'Georgia', serif;
    font-size: 1.2rem;
    line-height: 1.6;
    text-align: left;
    transition: all 0.3s ease;
  }

  p {
    margin: 0;
  }

  @media (max-width: 768px) {
    .article-text {
      width: 90%;
      padding: 1.25rem 1.5rem;
      font-size: 1rem;
    }
  }
</style>
