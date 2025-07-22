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
        background-color: #ffffff; /* clean white base */
        padding: min(100vh, 30rem) 1rem;
        border: 4px solid #f8dce0; /* pale pink border */
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-items: flex-start;
        font-family: 'Georgia', serif;
        color: #0a1a40; /* navy text */
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
        display: flex;
        flex-direction: column;
        flex: 1 1;
        padding: 1rem;
    }

    .sticky {
        position: sticky;
        top: 50vh;
        transform: translateY(-50%);
        align-items: center;
        justify-content: center;
        background-color: #f0f3f8; /* soft off-white for contrast */
        border-radius: 1rem;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        z-index: 0;
    }

    .scrolly {
        z-index: 1;
    }

    @media (max-width: 768px) {
        .wrapper {
            flex-direction: column;
            padding: 2rem 1rem;
            width: 100vw;
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
            margin-bottom: 2rem;
        }
    }
</style>
