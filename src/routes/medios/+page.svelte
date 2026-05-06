<script>
    import { base } from '$app/paths';
    const mediaItems = [
        {
            outlet: "El Conquistador",
            title: "Un beso y chao - Marcela Martínez Bascuñán directora de Estudios de City Lab Biobío",
            date: "01-04-2026",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=53406983&email=558836&fromemail=1",
            type: "Sitio web"
        },
        {
            outlet: "Radio UdeC",
            title: "Entrevista a Marcela Martínez, directora de estudios de City Lab Biobío, sobre la iniciativa 'Un Beso y Chao'",
            date: "01-04-2026",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=53406981&email=558836&fromemail=1",
            type: "Radio"
        },
        {
            outlet: "TVU",
            title: "Entrevista a Marcela Martínez, Directora de estudios City Lab Biobío, Beso y Chao promueve descensos rápidos",
            date: "07-04-2026",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=53509752&email=559616&fromemail=1",
            type: "Televisión"
        },
        {
            outlet: "Diario Concepción",
            title: "Un Beso y Chao: propuesta busca optimizar tiempos de traslado en zonas escolares",
            date: "08-04-2026",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=53511443&email=559616&fromemail=1",
            type: "Sitio web"
        },
        {
            outlet: "Mundo Marítimo",
            title: "Sistema portuario de Chile: Coordinación y tecnología emergen como claves para superar ...",
            date: "16-04-2026",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=53734494&email=561435&fromemail=1",
            type: "Sitio web"
        },
        {
            outlet: "El Mercurio",
            title: "Expertos plantean desafíos a viviendas de integración social y su aplicación en regiones",
            date: "27-04-2026",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=53872560&email=562591&fromemail=1",
            type: "Prensa escrita"
        },
        {
            outlet: "El Sur",
            title: "Piloto para agilizar el tránsito en colegio penquista disminuye congestión al 50%",
            date: "06-05-2026",
            url: "https://map.conectamedia.cl/index.php/clippingNews/view?id=54042834&email=563974&fromemail=1",
            type: "Prensa escrita",
        }
    ];
</script>

<main>
    <div class="container">
        <header>
            <a href="{base}/" class="back-link">← Volver</a>
            <h1>El lab en medios</h1>
            <p class="tagline">Abril - Mayo 2026</p>
        </header>

        <section class="media-grid" aria-label="Apariciones en medios">
            {#each mediaItems as item}
                <a href={item.url} class="media-card" target="_blank" rel="noopener noreferrer">
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
