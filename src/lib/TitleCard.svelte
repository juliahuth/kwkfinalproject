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
        background-color: #0a1a40; /* deep navy */
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 2rem;
        box-sizing: border-box;
        font-family: 'Impact', 'Segoe UI', sans-serif; /* bold, impactful */
    }

    .content {
        max-width: 700px;
        background-color: white;
        padding: 2rem 2.5rem;
        border: 4px solid #f8dce0; /* pale pink */
        border-radius: 1.5rem;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
    }

    h1 {
        font-size: 3rem;
        margin: 0;
        color: #0a1a40; /* navy */
        letter-spacing: 1px;
    }

    p {
        font-size: 1.3rem;
        color: #444;
        margin-top: 1rem;
        font-family: 'Georgia', serif; /* adds class */
    }

    @media (max-width: 600px) {
        h1 {
            font-size: 2.2rem;
        }

        p {
            font-size: 1.1rem;
        }
    }
</style>
