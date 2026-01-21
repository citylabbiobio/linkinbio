<script>
    // Datos (const donde no se mutan)
    const mainLinks = [
        {
            title: "Microestudios",
            description: "Investigación urbana aplicada",
            url: "https://citylabbiobio.cl/documentos-y-estudios",
        },
        {
            title: "Noticias",
            description: "Lo último del laboratorio",
            url: "https://citylabbiobio.cl/noticias",
        },
        {
            title: "City Science Summit 2025",
            description: "Event Hub & Documentación",
            url: "https://citylabbiobio.cl/cities-in-transition",
        },
        {
            title: "Microdocumentales",
            description: "Los desafíos del Summit junto a City Science Network",
            url: "https://www.youtube.com/playlist?list=PL_C8grluozpiPrphpb5u-CTLS2btH_Az0",
        },
        {
            title: "Reporte Incendios 2026",
            description: "Temporada Incendios Forestales en el Biobío",
            url: "reporteincendios.citylabbiobio.cl",
        },
        {
            title: "Contacto",
            description: "Conectemos",
            url: "mailto:contacto@citylabbiobio.cl",
        },
        {
            title: "Transparencia",
            description: "Nuestros procesos abiertos",
            url: "https://citylabbiobio.cl/laboratorio-transparente/",
        }
    ];

    const socialLinks = [
        {
            platform: "Instagram",
            url: "https://instagram.com/citylabbiobio",
            icon: "instagram"
        },
        {
            platform: "LinkedIn",
            url: "https://linkedin.com/company/citylabbiobio",
            icon: "linkedin"
        },
        {
            platform: "YouTube",
            url: "https://youtube.com/@citylabbiobio",
            icon: "youtube"
        }
    ];

    // Gallery muta porque controlamos active
    let gallery = [

        {
            id: "i1",
            type: "image",
            src: "https://d26q11cgz8q0ri.cloudfront.net/2025/11/24162014/MSB-6-scaled.png",
            alt: "Metropolitan Scope Biobío",
            active: false
        },
        {
            id: "i2",
            type: "image",
            src: "https://d26q11cgz8q0ri.cloudfront.net/2025/11/24161234/CLBB-13-scaled.jpg",
            alt: "CityScope Costanera",
            active: false
        },
        {
            id: "i3",
            type: "image",
            src: "https://d26q11cgz8q0ri.cloudfront.net/2025/09/12233626/foto-Talcahuano.avif",
            alt: "Ciudad Portuaria Talcahuano",
            active: false
        },
        {
            id: "i4",
            type: "image",
            src: "https://d26q11cgz8q0ri.cloudfront.net/2025/11/24162242/EtMday-2025-108-scaled.jpg",
            alt: "Vinculación con el medio",
            active: false
        },
        {
            id: "i5",
            type: "image",
            src: "https://d26q11cgz8q0ri.cloudfront.net/2025/11/17231645/MM6A4701.jpg",
            alt: "Summit Cities in Transition",
            active: false
        },
        {
            id: "i5",
            type: "image",
            src: "https://d26q11cgz8q0ri.cloudfront.net/2025/10/28172052/CCP-3.jpg",
            alt: "Investigación aplicada en ciudad",
            active: false
        },
        {
            id: "i3",
            type: "image",
            src: "https://d26q11cgz8q0ri.cloudfront.net/2025/11/25151856/Jordy-scaled.png",
            alt: "Opinión",
            active: false
        },
        {
            id: "i4",
            type: "image",
            src: "https://d26q11cgz8q0ri.cloudfront.net/2025/11/25152357/EtMday-2025-099-scaled.jpg",
            alt: "",
            active: false
        }

    ];

    // Toggle: solo uno puede estar activo, y si se vuelve a clickear se desactiva
    function handleGalleryClick(index) {
        gallery = gallery.map((item, i) => {
            if (i === index) return { ...item, active: !item.active };
            return { ...item, active: false };
        });
    }

    // Utility: SVG icons como strings (seguros, estáticos)
    const icons = {
        instagram: `<svg viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>`,

        linkedin: `<svg viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>`,

        youtube: `<svg viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z"/></svg>`
    };
</script>

<main>
    <div class="container">
        <!-- Header -->
        <header>
            <div class="logo">
                <img src="https://d26q11cgz8q0ri.cloudfront.net/2025/09/25000646/LOGO-CLBB-ORIGINAL-NEGRO-APAISADO.png" alt="City Lab Biobío" />
            </div>
            <h1>City Lab Biobío</h1>
            <p class="tagline">Ciencia de ciudad al sur del mundo</p>
        </header>

        <!-- Main Links -->
        <section class="links-section" aria-labelledby="links-title">
            <h2 id="links-title" class="visually-hidden">Enlaces principales</h2>
            <div class="links-grid">
                {#each mainLinks as link}
                    <a href={link.url} class="link-block" target="_blank" rel="noopener noreferrer" aria-label={link.title}>
                        <h2>{link.title}</h2>
                        <p>{link.description}</p>
                    </a>
                {/each}
            </div>
        </section>

        <section class="social-section">
            <div class="social-links">
                {#each socialLinks as social}
                    <a
                            href={social.url}
                            class="social-link"
                            target="_blank"
                            rel="noopener noreferrer"
                            aria-label={social.platform}
                    >
                        {#if social.icon === "instagram"}
                            <svg viewBox="0 0 24 24" fill="currentColor">
                                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
                            </svg>
                        {:else if social.icon === "linkedin"}
                            <svg viewBox="0 0 24 24" fill="currentColor">
                                <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                            </svg>
                        {:else if social.icon === "youtube"}
                            <svg viewBox="0 0 24 24" fill="currentColor">
                                <path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z"/>
                            </svg>
                        {/if}
                    </a>
                {/each}
            </div>
        </section>

        <!-- Gallery -->
        {#if false}
        <section class="gallery-section" aria-labelledby="gallery-title">
            <h2 id="gallery-title" class="section-title">Destacados</h2>
            <div class="gallery" role="list">
                {#each gallery as item, index (item.id)}
                    <div
                            class="gallery-item {item.active ? 'active' : ''}"
                            role="listitem"
                    >
                        <!-- Usamos un button para accesibilidad; solo cargamos iframe si está activo -->
                        <button
                                class="gallery-button"
                                on:click={() => handleGalleryClick(index)}
                                aria-pressed={item.active}
                                aria-label={item.alt}
                        >
                            {#if item.type === "image"}
                                <img src={item.src} alt={item.alt} loading="lazy" />
                            {:else if item.type === "video"}
                                {#if item.active}
                                    <div class="video-container">
                                        <iframe
                                                src={item.src}
                                                title={item.alt}
                                                frameborder="0"
                                                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                                                allowfullscreen
                                        ></iframe>
                                    </div>
                                {:else}
                                    <!-- Placeholder: icono de play + alt text (no cargamos iframe hasta activación) -->
                                    <div class="video-placeholder" aria-hidden="true">
                                        <svg viewBox="0 0 24 24" fill="currentColor" class="play-icon"><path d="M8 5v14l11-7z"/></svg>
                                    </div>
                                {/if}
                            {/if}
                            <div class="gallery-overlay">
                                <span>{item.alt}</span>
                            </div>
                        </button>
                    </div>
                {/each}
            </div>
        </section>
            {/if}

        <!-- Footer -->
        <footer>
            <p><b>Ciencia de ciudad al sur del mundo</b></p>
            <p>Arturo Prat 525, Concepción - Región del Biobío</p>

            <div class="collaboration">
                <div class="logos">
                    <img src="https://d26q11cgz8q0ri.cloudfront.net/2025/11/24115707/GORE-NEGRO.png" alt="Gobierno Regional del Biobío" />
                    <img src="https://d26q11cgz8q0ri.cloudfront.net/2025/11/24115656/CC-negro.png" alt="Corporación Ciudades" />
                    <img src="https://d26q11cgz8q0ri.cloudfront.net/2025/11/24115650/CCHC-negro%404x.png" alt="Cámara Chilena de la Construcción" />
                </div>
            </div>

            <div class="collaboration">
                <p class="collaboration-text">En cooperación con</p>
                <div class="logos">
                    <img src="https://d26q11cgz8q0ri.cloudfront.net/2025/11/24120604/mit-media_1-scaled.png" alt="MIT Media Lab" class="mit-logo"/>
                    <img src="https://d26q11cgz8q0ri.cloudfront.net/2025/11/24145037/CS_Logo_K_RGB.png" alt="MIT City Science" class="mit-logo" />
                </div>
            </div>
        </footer>
    </div>
</main>

<style>
    /* small helper */
    .visually-hidden {
        position: absolute !important;
        height: 1px; width: 1px;
        overflow: hidden;
        clip: rect(1px, 1px, 1px, 1px);
        white-space: nowrap;
    }

    /* Global Resets */
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
        text-align: center;
        margin-bottom: 4rem;
        padding: 2rem 0;
    }

    .logo {
        width: 200px;
        height: auto;
        margin: 0 auto 1.5rem;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .logo img {
        width: 100%;
        height: auto;
        display: block;
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
        font-weight: 400;
    }

    /* LINKS: color gris oscuro (#333) */
    .links-section {
        margin-bottom: 4rem;
    }

    .links-grid {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 1rem;
    }

    .link-block {
        background: white;
        padding: 2rem;
        border-radius: 8px;
        text-decoration: none;
        color: #333; /* <--- gris oscuro */
        border: 1px solid #e5e5e5;
        transition: all 0.18s ease;
        display: block;
    }

    .link-block h2 {
        font-size: 1.25rem;
        font-weight: 600;
        margin-bottom: 0.5rem;
    }

    .link-block p {
        font-size: 0.9rem;
        color: #666;
    }

    .link-block:hover,
    .link-block:focus {
        border-color: #1a1a1a;
        transform: translateY(-2px);
        outline: none;
        box-shadow: 0 6px 18px rgba(0,0,0,0.04);
    }

    /* Social */
    .social-section {
        margin-bottom: 4rem;
        text-align: center;
    }

    .social-links {
        display: flex;
        gap: 1rem;
        justify-content: center;
    }

    .social-link {
        width: 48px;
        height: 48px;
        background: white;
        border: 1px solid #e5e5e5;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 0.18s ease;
        color: #333; /* gris oscuro por defecto */
        text-decoration: none;
    }

    .social-link:hover,
    .social-link:focus {
        background: #1a1a1a;
        border-color: #1a1a1a;
        color: #fff;
        outline: none;
        transform: translateY(-2px);
    }

    .social-link svg {
        width: 20px;
        height: 20px;
    }

    /* Gallery */
    .gallery-section {
        margin-bottom: 4rem;
    }

    .section-title {
        font-size: 1.5rem;
        font-weight: 600;
        margin-bottom: 2rem;
        text-align: center;
    }

    .gallery {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-auto-rows: 200px;
        gap: 1rem;
    }

    .gallery-item {
        position: relative;
        background: white;
        border-radius: 8px;
        overflow: hidden;
        border: 1px solid #e5e5e5;
    }

    .gallery-button {
        display: block;
        width: 100%;
        height: 100%;
        padding: 0;
        border: 0;
        background: transparent;
        text-align: left;
        cursor: pointer;
        position: relative;
    }

    .gallery-button:focus {
        outline: 3px solid rgba(34,34,34,0.12);
    }

    .gallery-item:nth-child(1) { grid-column: span 1; grid-row: span 2; }
    .gallery-item:nth-child(2) { grid-column: span 1; grid-row: span 2; }
    .gallery-item:nth-child(3) { grid-column: span 2; grid-row: span 1; }
    .gallery-item:nth-child(4) { grid-column: span 2; grid-row: span 2; }
    .gallery-item:nth-child(5) { grid-column: span 2; grid-row: span 1; }
    .gallery-item:nth-child(6) { grid-column: span 2; grid-row: span 1; }

    .gallery-item img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        display: block;
    }

    .video-container {
        width: 100%;
        height: 100%;
        position: relative;
    }

    .video-container iframe {
        width: 100%;
        height: 100%;
        position: absolute;
        top: 0;
        left: 0;
    }

    .video-placeholder {
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        background: linear-gradient(180deg, #111 0%, #333 100%);
    }

    .play-icon {
        width: 64px;
        height: 64px;
        color: white;
        opacity: 0.95;
    }

    .gallery-overlay {
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        background: linear-gradient(to top, rgba(0,0,0,0.85), rgba(0,0,0,0.3));
        color: white;
        padding: 1.25rem;
        opacity: 0;
        transition: opacity 0.22s ease;
        pointer-events: none;
    }

    .gallery-overlay span { font-size: 0.9rem; font-weight: 500; display: block; }

    @media (hover: hover) {
        .gallery-item:hover .gallery-overlay { opacity: 1; }
    }

    @media (hover: none) {
        .gallery-item.active .gallery-overlay { opacity: 1; }
        .gallery-overlay { top: 0; bottom: 0; background: rgba(0,0,0,0.6); display:flex; align-items:center; padding:1.5rem; }
        .gallery-overlay span { font-size: 1.1rem; text-align: left; line-height:1.4; }
    }

    /* Footer */
    footer {
        text-align: center;
        padding: 2rem 0;
        color: #666;
        font-size: 0.9rem;
    }

    .collaboration {
        margin-top: 3rem;
        padding-top: 2rem;
        border-top: 1px solid #e5e5e5;
    }

    .collaboration-text {
        font-size: 0.85rem;
        text-transform: uppercase;
        letter-spacing: 1px;
        color: #999;
        margin-bottom: 1.5rem;
    }

    .logos {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        gap: 2rem;
        flex-wrap: wrap;
    }

    .logos img {
        height: 50px;
        width: auto;
        max-width: 110px;
        object-fit: contain;
        opacity: 0.6;
        transition: opacity 0.2s ease;
        filter: grayscale(100%);
    }

    .logos img:hover { opacity: 1; filter: grayscale(0%); }

    .mit-logo { height: 40px !important; }

    /* Responsive */
    @media (max-width: 768px) {
        h1 { font-size: 2rem; }
        .links-grid { grid-template-columns: 1fr; }
        .gallery { grid-template-columns: repeat(2, 1fr); grid-auto-rows: 180px; }

        .gallery-item:nth-child(1),
        .gallery-item:nth-child(2),
        .gallery-item:nth-child(3),
        .gallery-item:nth-child(4),
        .gallery-item:nth-child(5),
        .gallery-item:nth-child(6) {
            grid-column: span 1;
            grid-row: span 1;
        }

        .gallery-item:nth-child(1),
        .gallery-item:nth-child(2) { grid-row: span 2; }
        .gallery-item:nth-child(3) { grid-column: span 2; }
        .gallery-item:nth-child(4) { grid-column: span 2; grid-row: span 2; }

        .logos { gap: 1.5rem; }
        .logos img { height: 40px; max-width: 90px; }
        .mit-logo { height: 32px !important; }
    }

    @media (max-width: 480px) {
        .gallery { grid-template-columns: 1fr; grid-auto-rows: 250px; }
        .gallery-item:nth-child(1), .gallery-item:nth-child(2) { grid-row: span 2; }
    }
</style>
