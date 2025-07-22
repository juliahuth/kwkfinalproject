<script>
    import { onMount } from "svelte";

    let { children, callback, options } = $props();

    // Unique ID to target this element
    let uniqueId = Math.random().toString();

    onMount(() => {
        let intersectionObserver = new IntersectionObserver(callback, options);
        const observedElement = document.getElementById(uniqueId);
        intersectionObserver.observe(observedElement);
    });
</script>

<!-- assign the containing div the id `uniqueId` so we can target it -->
<div id={uniqueId} class="article-text">
    <p>
        {@render children()}
    </p>
</div>

<style>
    .article-text {
        margin: 50vh auto;
        width: 60%;
        background-color: #ffffff; /* white background */
        color: #0a1a40; /* navy text */
        border: 3px solid #f8dce0; /* pale pink accent */
        border-radius: 1rem;
        padding: 2rem;
        box-shadow: 0 8px 24px rgba(10, 26, 64, 0.15); /* subtle navy shadow */
        font-family: 'Georgia', serif;
        line-height: 1.6;
        text-align: left;
    }

    p {
        margin: 0;
        font-size: 1.2rem;
    }

    @media (max-width: 768px) {
        .article-text {
            width: 90%;
            padding: 1.5rem;
        }

        p {
            font-size: 1rem;
        }
    }
</style>
