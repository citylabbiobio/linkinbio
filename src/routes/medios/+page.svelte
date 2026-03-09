<script>
    const mediaItems = [
        {
            outlet: "El Sur",
            logo: "https://d26q11cgz8q0ri.cloudfront.net/2026/03/06113333/El-sur.png ",
            title: "San Pedro de la Paz registraría retraso vial de hasta 50 minutos en el “súper lunes",
            date: "02-03-2026",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=52779094&email=553514&fromemail=1",
            type: "Prensa escrita"
        },
        {
            outlet: "HoyxHoy Concepción",
            logo: "https://d26q11cgz8q0ri.cloudfront.net/2026/03/06120236/28.png",
            title: "Superlunes tuvo tacos de hasta 50 minutos y velocidad de 4 km/h",
            date: "04-03-2026",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=52826752&email=553944&fromemail=1",
            type: "Digital"
        },
        {
            outlet: "Radio Bío-Bío",
            logo: "https://d26q11cgz8q0ri.cloudfront.net/2026/03/06113319/biobio-radio.png",
            title: "Entrevista a Fernando Pérez, director principal de City Lab Biobío, sobre impacto vial del 'súper lunes' en el Gran Concepción",
            date: "04-03-2025",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=52807603&email=553944&fromemail=1",
            type: "Radio"
        },
        {
            outlet: "Radio UdeC",
            logo: "https://d26q11cgz8q0ri.cloudfront.net/2026/03/06115231/Radio-UdeC.png",
            title: "Entrevista a Fernando Pérez, director principal de City Lab Biobío, por informe sobre impacto vial del 'súper lunes' en el Gran Concepción",
            date: "04-03-206",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=52806131&email=553944&fromemail=1",
            type: "Prensa escrita"
        },
    ];
</script>

<main>
    <div class="container">
        <header>
            <a href="/" class="back-link">← Volver</a>
            <h1>El lab en medios</h1>
            <p class="tagline">Marzo 2026</p>
        </header>

        <section class="media-grid" aria-label="Apariciones en medios">
            {#each mediaItems as item}
                <a href={item.url} class="media-card" target="_blank" rel="noopener noreferrer">
                    <div class="media-logo">
                        <img src={item.logo} alt={item.outlet} />
                    </div>
                    <div class="media-content">
                        <span class="media-type">{item.type}</span>
                        <span class="media-outlet">{item.outlet}</span>
                        <h2>{item.title}</h2>
                        <span class="media-date">{item.date}</span>
                    </div>
                </a>
            {/each}
        </section>

        <footer>
            <p><b>Ciencia de ciudad al sur del mundo</b></p>
            <p>Arturo Prat 525, Concepción - Región del Biobío</p>
        </footer>
    </div>
</main>

<style>
    :global(*) {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    :global(body) {
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Inter', sans-serif;
        background: #fafafa;
        color: #1a1a1a;
        line-height: 1.6;
    }

    main {
        min-height: 100vh;
        padding: 2rem 1rem;
    }

    .container {
        max-width: 1000px;
        margin: 0 auto;
    }

    header {
        margin-bottom: 3rem;
        padding: 2rem 0;
    }

    .back-link {
        display: inline-block;
        margin-bottom: 1.5rem;
        color: #666;
        text-decoration: none;
        font-size: 0.9rem;
        transition: color 0.18s ease;
    }

    .back-link:hover {
        color: #1a1a1a;
    }

    h1 {
        font-size: 2.5rem;
        font-weight: 700;
        margin-bottom: 0.5rem;
        letter-spacing: -1px;
    }

    .tagline {
        font-size: 1rem;
        color: #666;
    }

    .media-grid {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 1rem;
        margin-bottom: 4rem;
    }

    .media-card {
        background: white;
        border: 1px solid #e5e5e5;
        border-radius: 8px;
        padding: 1.5rem;
        text-decoration: none;
        color: #333;
        display: flex;
        flex-direction: row;
        gap: 1.25rem;
        align-items: center;
        transition: all 0.18s ease;
    }

    .media-logo {
        flex-shrink: 0;
        width: 80px;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .media-logo img {
        width: 80px;
        height: 40px;
        object-fit: contain;
        filter: brightness(0);
    }

    .media-content {
        display: flex;
        flex-direction: column;
        gap: 0.35rem;
        flex: 1;
    }

    .media-card:hover,
    .media-card:focus {
        border-color: #1a1a1a;
        transform: translateY(-2px);
        outline: none;
        box-shadow: 0 6px 18px rgba(0, 0, 0, 0.04);
    }

    .media-type {
        font-size: 0.75rem;
        text-transform: uppercase;
        letter-spacing: 1px;
        color: #999;
    }

    .media-outlet {
        font-size: 0.85rem;
        font-weight: 600;
        color: #1a1a1a;
    }

    .media-card h2 {
        font-size: 1rem;
        font-weight: 500;
        line-height: 1.4;
        margin-top: 0.25rem;
        flex: 1;
    }

    .media-date {
        font-size: 0.8rem;
        color: #999;
        margin-top: 0.5rem;
    }

    footer {
        text-align: center;
        padding: 2rem 0;
        color: #666;
        font-size: 0.9rem;
        border-top: 1px solid #e5e5e5;
    }

    footer p + p {
        margin-top: 0.25rem;
    }

    @media (max-width: 768px) {
        h1 { font-size: 2rem; }
        .media-grid { grid-template-columns: 1fr; }
    }
</style>
