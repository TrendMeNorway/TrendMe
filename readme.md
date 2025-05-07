<!DOCTYPE html>
<html lang="no">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TrendMe | ESG Rapportering med Microsoft Fabric</title>
    <meta name="description" content="TrendMe tilbyr rådgivning og implementering for datadrevet ESG-rapportering ved hjelp av Microsoft Fabric. Oppfyll regulatoriske krav og få innsikt i din bærekraftytelse.">
    <link rel="icon" href="https://res.cloudinary.com/dm2movu5v/image/upload/f_auto,q_auto/v1746189579/SVG_yqf4t8.svg" type="image/svg+xml">
    <link rel="icon" type="image/png" sizes="32x32" href="https://res.cloudinary.com/dm2movu5v/image/upload/f_auto,q_auto/v1746189607/icon_rdwy3d.png">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

    <style>
        /* === KOPIER ALL CSS FRA DIN ORIGINALE SIDE HER === */
        /* Lim inn *hele* <style>-blokken fra din forrige HTML-fil her */
        /* Dette inkluderer :root, *, html, body, .container, .fade-in, header, .hero, .section, osv. */
        :root {
            --bg-light: #ffffff;
            --bg-soft-light: #f8f9fa;
            --text-dark-primary: #212529;
            --text-dark-secondary: #495057;
            --text-dark-muted: #6c757d;
            --card-border-light: rgba(0, 0, 0, 0.1);
            --header-bg-light: rgba(255, 255, 255, 0.85);
            --suggestions-bg-light: rgba(255, 255, 255, 0.98);
            --suggestions-hover-bg-light: #f1f3f5;
            --footer-bg-light: #f1f3f5;
            --primary-accent-dark: #0078d4; /* Blå Microsoft */
            --primary-accent-light: #00c6ff; /* Lysere blå */
            --secondary-accent: #00b050; /* Grønn for ESG */
            --secondary-accent-light: #70c48f; /* Lysere grønn for ESG */
            --glow-color: rgba(0, 176, 80, 0.3); /* Grønnaktig glow for ESG */
            --button-glow-color: rgba(0, 176, 80, 0.2); /* Grønnaktig knappeglow */
            --text-on-accent: #ffffff;
            --text-on-dark-bg: #1f1f1f; /* Mørk tekst på lys bakgrunn for CTA etc. */
            --font-primary: 'Poppins', sans-serif;
            --transition-speed: 0.3s;
            --transition-slow: 0.5s;
            --error-color: #dc3545;
            --header-height: 70px;
        }
        * { box-sizing: border-box; margin: 0; padding: 0; }
        html { scroll-behavior: smooth; scrollbar-width: thin; scrollbar-color: var(--secondary-accent) var(--bg-soft-light); } /* Endret scrollbar-farge til ESG-grønn */
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: var(--bg-soft-light); }
        ::-webkit-scrollbar-thumb { background-color: var(--secondary-accent); border-radius: 10px; border: 2px solid var(--bg-soft-light); } /* Endret scrollbar-farge til ESG-grønn */
        body { font-family: var(--font-primary); line-height: 1.7; color: var(--text-dark-secondary); background-color: var(--bg-light); overflow-x: hidden; background: linear-gradient(135deg, #f0f7f2 0%, #ffffff 50%, #e6f2ff 100%); } /* Litt grønnere start på gradient */
        .container { max-width: 1200px; margin: auto; padding: 0 25px; }
        .fade-in { opacity: 0; transition: opacity 1s ease-out, transform 0.8s ease-out; }
        .slide-up { transform: translateY(40px); }
        .slide-left { transform: translateX(-40px); }
        .slide-right { transform: translateX(40px); }
        .visible { opacity: 1; transform: translate(0, 0) !important; }
        header { background: var(--header-bg-light); backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px); color: var(--text-dark-primary); padding: 0.5rem 0; position: sticky; top: 0; z-index: 1000; border-bottom: 1px solid var(--card-border-light); transition: background-color var(--transition-speed) ease; height: var(--header-height); }
        header nav { display: flex; justify-content: space-between; align-items: center; height: 100%; }
        .logo-link { display: flex; align-items: center; height: 100%; }
        .logo-img { display: block; max-height: calc(var(--header-height) - 25px); width: auto; transition: transform 0.3s ease; }
        .logo-img:hover { transform: scale(1.05); }
        header ul { list-style: none; display: flex; align-items: center; flex-wrap: wrap; justify-content: flex-end; margin-top: 0; padding: 0; height: 100%; }
        header ul li { margin-left: 20px; }
        header ul li a { display: flex; align-items: center; color: var(--text-dark-muted); text-decoration: none; padding: 10px 15px; transition: color var(--transition-speed) ease; border-radius: 5px; font-weight: 400; font-size: 0.95rem; letter-spacing: 0.5px; position: relative; overflow: hidden; white-space: nowrap; }
        header ul li a::after { content: ''; position: absolute; width: 0; height: 2px; bottom: 5px; left: 50%; background: linear-gradient(90deg, var(--secondary-accent-light), var(--secondary-accent)); transition: width var(--transition-speed) ease, left var(--transition-speed) ease; transform: translateX(-50%); } /* Endret gradient til ESG-farger */
        header ul li a:hover { color: var(--secondary-accent); } /* Hoverfarge til ESG-grønn */
        header ul li a:hover::after { width: 70%; left: 50%; }
        /* Hero for ESG siden */
        .hero-esg { min-height: 70vh; display: flex; align-items: center; justify-content: center; text-align: center; padding: 7rem 0 4rem 0; position: relative; overflow: hidden; background: linear-gradient(160deg, rgba(0, 176, 80, 0.1) 0%, rgba(255, 255, 255, 0.8) 70%), linear-gradient(135deg, #eef7f2 0%, #ffffff 100%); } /* ESG-grønn gradient */
        .hero-esg .container { position: relative; z-index: 2; }
        .hero-esg h1 { font-size: 3.2rem; font-weight: 700; margin-bottom: 1.5rem; line-height: 1.2; color: var(--text-dark-primary); animation: text-focus-in 1.5s cubic-bezier(0.550, 0.085, 0.680, 0.530) both; }
        @keyframes text-focus-in { 0% { filter: blur(8px); opacity: 0; } 100% { filter: blur(0px); opacity: 1; } }
        .hero-esg .typing-container { font-size: 1.3rem; color: var(--text-dark-secondary); margin-bottom: 2.5rem; min-height: 1.8em; }
        .typing-cursor { display: inline-block; width: 10px; height: 1.3rem; background-color: var(--secondary-accent); margin-left: 5px; animation: blink 0.7s infinite; vertical-align: bottom; } /* ESG-grønn cursor */
        @keyframes blink { 50% { opacity: 0; } }
        .hero-cta-container { margin-top: 2.5rem; }
        .cta-button { display: inline-flex; align-items: center; justify-content: center; gap: 0.8em; padding: 15px 35px; text-decoration: none; border-radius: 50px; font-weight: 600; transition: transform var(--transition-speed) ease, box-shadow var(--transition-speed) ease, background var(--transition-speed) ease, border-color var(--transition-speed) ease, color var(--transition-speed) ease; border: none; cursor: pointer; font-size: 1.1rem; white-space: nowrap; background: linear-gradient(90deg, var(--secondary-accent-light), var(--secondary-accent)); color: var(--text-on-dark-bg); box-shadow: 0 5px 15px var(--button-glow-color); } /* ESG-grønn CTA */
        .cta-button:hover { transform: translateY(-5px) scale(1.05); box-shadow: 0 10px 25px var(--glow-color); } /* ESG-grønn glow */
        .cta-button:disabled { background: #adb5bd; color: #6c757d; cursor: not-allowed; opacity: 0.7; transform: none; box-shadow: none; }
        .section { padding: 5rem 0; overflow: hidden; } /* Litt mindre padding for undersider */
        .section-header { text-align: center; margin-bottom: 4rem; }
        .section-header span { display: block; font-size: 1rem; color: var(--secondary-accent); text-transform: uppercase; letter-spacing: 1px; margin-bottom: 0.5rem; font-weight: 600; } /* ESG-grønn span */
        .section-header h2 { font-size: 2.6rem; font-weight: 700; color: var(--text-dark-primary); margin-bottom: 1rem; position: relative; display: inline-block; }
        .section-header h2::after { content: ''; position: absolute; width: 60px; height: 4px; background: linear-gradient(90deg, var(--secondary-accent-light), var(--secondary-accent)); bottom: -15px; left: 50%; transform: translateX(-50%); border-radius: 2px; } /* ESG-grønn linje */
        .section-header p { max-width: 700px; margin: 1.5rem auto 0 auto; color: var(--text-dark-secondary); font-size: 1.1rem; }
        .services-bg { background: var(--bg-soft-light); }
        .service-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 2.5rem; }
        .service-card { background: var(--bg-light); border: 1px solid var(--card-border-light); border-radius: 12px; padding: 2.5rem 2rem; transition: transform var(--transition-speed) ease, box-shadow var(--transition-speed) ease, border-color var(--transition-speed) ease; overflow: hidden; position: relative; box-shadow: 0 5px 15px rgba(0, 0, 0, 0.03); }
        .service-card:hover { transform: translateY(-8px); box-shadow: 0 12px 25px rgba(0, 0, 0, 0.08); border-color: var(--secondary-accent); } /* ESG-grønn border på hover */
        .service-card > * { position: relative; z-index: 1; }
        .service-icon-container { margin-bottom: 1.5rem; text-align: center; min-height: 65px; display: flex; justify-content: center; align-items: center; }
        .service-icon { width: auto; max-width: 55px; height: 55px; object-fit: contain; }
        .service-icon.esg-icon { filter: hue-rotate(60deg) brightness(0.9); } /* Gjenbruk eksisterende ikoner med grønnfarge-justering om nødvendig, eller bruk nye ESG-ikoner */
        .service-card h3 { font-size: 1.6rem; margin-bottom: 1rem; color: var(--text-dark-primary); text-align: center; }
        .service-card ul { list-style: none; padding: 0; margin-top: 1.5rem; }
        .service-card ul li { margin-bottom: 0.8rem; position: relative; padding-left: 25px; color: var(--text-dark-secondary); font-size: 0.95rem; }
        .service-card ul li::before { content: '>'; position: absolute; left: 0; color: var(--secondary-accent); font-weight: bold; font-size: 1.2rem; line-height: 1; top: 2px; transition: transform var(--transition-speed) ease; } /* ESG-grønn listeprikk */
        .service-card:hover ul li::before { transform: translateX(3px); }
        #kontakt { background: var(--bg-soft-light); }
        #contact-form { max-width: 700px; margin: 0 auto; background: var(--bg-light); padding: 3rem; border-radius: 15px; border: 1px solid var(--card-border-light); box-shadow: 0 10px 30px rgba(0, 0, 0, 0.07); }
        .form-group { margin-bottom: 1.8rem; position: relative; }
        .form-group label { display: block; margin-bottom: 0.7rem; font-weight: 600; color: var(--text-dark-muted); font-size: 0.9rem; text-transform: uppercase; letter-spacing: 0.5px; }
        .form-group input[type="text"], .form-group input[type="email"], .form-group input[type="tel"], .form-group textarea { width: 100%; padding: 1rem; border: 1px solid var(--card-border-light); border-radius: 8px; font-family: inherit; font-size: 1rem; background-color: #fff; color: var(--text-dark-primary); transition: border-color var(--transition-speed) ease, box-shadow var(--transition-speed) ease; }
        .form-group input:focus, .form-group textarea:focus { outline: none; border-color: var(--secondary-accent); box-shadow: 0 0 0 3px rgba(0, 176, 80, 0.15); } /* ESG-grønn focus */
        .form-group textarea { resize: vertical; min-height: 120px; }
        #contact-form button[type="submit"] { display: block; width: 100%; margin-top: 1rem; padding: 15px 30px; background: linear-gradient(90deg, var(--secondary-accent-light), var(--secondary-accent)); color: var(--text-on-dark-bg); box-shadow: 0 5px 15px var(--button-glow-color);} /* ESG-grønn CTA */
        #form-error-message { color: var(--error-color); margin-top: 1rem; text-align: center; display: none; font-weight: 600; }
        footer { background-color: var(--footer-bg-light); color: var(--text-dark-muted); text-align: center; padding: 3rem 0 2rem 0; margin-top: 4rem; border-top: 1px solid var(--card-border-light); }
        footer p { margin-bottom: 1rem; font-size: 0.9rem; }
        .footer-links { margin-bottom: 1.5rem; }
        .footer-links a { display: inline-block; margin: 0 12px; transition: transform var(--transition-speed) ease, opacity var(--transition-speed) ease; opacity: 0.7; }
        .footer-links img { width: 28px; height: 28px; vertical-align: middle; filter: grayscale(50%) opacity(70%); transition: filter var(--transition-speed) ease; }
        .footer-links a:hover img { filter: grayscale(0%) opacity(1); }
        .footer-links a:hover { transform: scale(1.15); opacity: 1; }

        /* Legg til accordion-stiler hvis du vil bruke dem på denne siden også */
        .accordion-list { max-width: 900px; margin: 2rem auto 0 auto; }
        .accordion-item { border-bottom: 1px solid transparent; margin-bottom: 1rem; background: var(--bg-light); border-radius: 8px; box-shadow: 0 3px 8px rgba(0,0,0,0.03); border: 1px solid var(--card-border-light); }
        .accordion-title { background: none; border: none; color: var(--text-dark-primary); cursor: pointer; padding: 1.5rem 1rem; width: 100%; text-align: left; font-size: 1.3rem; font-weight: 600; font-family: inherit; display: flex; justify-content: space-between; align-items: center; transition: color var(--transition-speed) ease; }
        .accordion-title:hover, .accordion-title.aktiv { color: var(--secondary-accent); }
        .accordion-title span.tittel-tekst { flex-grow: 1; margin-right: 1rem; }
        .accordion-title span.ikon { font-size: 1.5rem; transition: transform var(--transition-slow) ease; transform-origin: center; display: inline-block; }
        .accordion-title.aktiv span.ikon { transform: rotate(45deg); }
        .accordion-content { max-height: 0; overflow: hidden; transition: max-height var(--transition-slow) ease-out, padding var(--transition-slow) ease-out, border-top var(--transition-slow) ease-out; padding: 0 1.5rem; color: var(--text-dark-secondary); font-size: 1rem; line-height: 1.8; border-top: 1px solid transparent; }
        .accordion-content.aktiv { padding: 1.5rem 1.5rem 2.5rem 1.5rem; overflow-y: auto; border-top: 1px solid var(--card-border-light); }
        .accordion-content ul { list-style: disc; padding-left: 25px; margin-top: 1rem; margin-bottom: 1rem; }
        .accordion-content ul li { margin-bottom: 0.5rem; padding-left: 0; color: var(--text-dark-secondary); }
        .accordion-content ul li::before { content: none; }
        .key-benefits-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem; margin-top: 3rem; }
        .benefit-item { background: var(--bg-soft-light); padding: 2rem; border-radius: 10px; border: 1px solid var(--card-border-light); }
        .benefit-item i { font-size: 2.5rem; color: var(--secondary-accent); margin-bottom: 1rem; display: block; text-align: center; }
        .benefit-item h4 { font-size: 1.25rem; color: var(--text-dark-primary); text-align: center; margin-bottom: 0.8rem; }
        .benefit-item p { font-size: 0.95rem; text-align: center; color: var(--text-dark-secondary); }

        /* Stiler for kontaktskjema-animasjon (hvis du vil gjenbruke) */
        #animation-container { position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; background-color: rgba(248, 249, 250, 0.9); display: none; justify-content: center; align-items: center; flex-direction: column; z-index: 1100; overflow: hidden; }
        #paper { background-color: #fff; width: 300px; height: 400px; box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1); border: 1px solid #dee2e6; padding: 20px; box-sizing: border-box; opacity: 0; transform: scale(0.8); transition: opacity 0.5s ease-out, transform 0.5s ease-out; position: relative; overflow: hidden; }
        #paper-content { font-family: var(--font-primary); font-size: 0.9rem; color: var(--text-dark-primary); white-space: pre-wrap; word-wrap: break-word; max-height: 100%; overflow-y: auto; }
        #thank-you-message { margin-top: 20px; font-size: 1.5rem; color: var(--secondary-accent); font-weight: bold; text-align: center; display: none; opacity: 0; transition: opacity 0.5s ease-in 0.2s; }
        @keyframes fly-away { 0% { transform: translate(0, 0) rotate(0deg) scale(1); opacity: 1; } 100% { transform: translate(120vw, -120vh) rotate(720deg) scale(0.1); opacity: 0; } }
        #paper.flying { animation: fly-away 2s ease-in forwards; }

        /* Responsive justeringer (kan trenge finjustering) */
        @media (max-width: 992px) {
             header nav { flex-direction: column; align-items: center; height: auto; min-height: var(--header-height); }
             .logo-link { margin-bottom: 10px; height: auto; } .logo-img { max-height: 40px; }
             header ul { justify-content: center; margin-top: 0; height: auto; flex-wrap: wrap; }
             header ul li { margin: 4px 6px; margin-left: 6px; }
             header ul li a { padding: 8px 12px; font-size: 0.9rem; white-space: normal; }
             header ul li a::after { bottom: 4px; } header ul li a:hover::after { width: 65%; }
             .hero-esg h1 { font-size: 2.8rem; } .hero-esg .typing-container { font-size: 1.2rem; }
             .section-header h2 { font-size: 2.2rem; }
             .service-grid { grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); }
        }
	    @media (max-width: 768px) {
            header { height: auto; min-height: var(--header-height); }
	        header ul li { margin: 3px 5px; margin-left: 5px; }
	        header ul li a { padding: 6px 10px; font-size: 0.85rem; }
	        header ul li a::after { bottom: 3px; } header ul li a:hover::after { width: 60%; }
	        .hero-esg { min-height: 60vh; padding: 5rem 0 3rem 0; } .hero-esg h1 { font-size: 2.2rem; }
	        .hero-esg .typing-container { font-size: 1rem; }
	        .cta-button { padding: 12px 30px; font-size: 1rem; }
	        .section { padding: 3.5rem 0; } .section-header h2 { font-size: 2rem; }
	        .section-header p { font-size: 1rem; } #contact-form { padding: 2rem; }
	        .service-grid { grid-template-columns: 1fr; }
	        .accordion-title { font-size: 1.1rem; padding: 1.2rem 0.8rem; }
	        .accordion-content { padding: 0 1rem; font-size: 0.95rem; }
	        .accordion-content.aktiv { padding: 1rem 1rem 2rem 1rem; }
            .key-benefits-grid { grid-template-columns: 1fr; }
	        #paper { width: 90%; max-width: 280px; height: auto; min-height: 350px; }
	        #thank-you-message { font-size: 1.2rem; }
	    }
        @media (max-width: 480px) {
            header ul li a { padding: 6px 8px; font-size: 0.8rem; }
            .hero-esg h1 { font-size: 1.8rem; } .section-header h2 { font-size: 1.6rem; }
            .footer-links img { width: 24px; height: 24px;} .footer-links a { margin: 0 8px;}
            #paper { max-width: 240px; min-height: 300px; padding: 15px; }
            #paper-content { font-size: 0.8rem;} #thank-you-message { font-size: 1.1rem; }
        }
        @media (min-width: 1800px) {
            header ul { flex-wrap: nowrap; }
            header ul li { margin-top: 0; margin-bottom: 0; margin-left: 20px; }
        }
    </style>
</head>
<body>
    <header id="main-header">
        <nav class="container">
            <a href="index.html" class="logo-link"> <!-- Lenker til hovedsiden -->
                <img src="https://res.cloudinary.com/dm2movu5v/image/upload/f_auto,q_auto/v1746189579/SVG_yqf4t8.svg" alt="TrendMe Logo" class="logo-img">
            </a>
            <ul>
                <li><a href="index.html#hjem">Hjem</a></li>
                <li><a href="index.html#om-oss">Om Oss</a></li>
		        <li><a href="index.html#hvorfor-moderne-data">Dataanalyse</a></li>
                <li><a href="index.html#fabric-tjenester">Fabric</a></li>
                <li><a href="index.html#powerbi-tjenester">Power BI</a></li>
                <li><a href="esg-rapportering.html">ESG-Rapportering</a></li> <!-- Aktiv lenke til denne siden -->
                <li><a href="index.html#ressurser">Ressurser</a></li>
                <li><a href="index.html#kontakt">Kontakt</a></li>
                <li><a href="/blogg">Blogg</a></li> <!-- Antar disse er separate sider/mapper -->
                <li><a href="/faktura">Faktura</a></li><!-- Antar disse er separate sider/mapper -->
            </ul>
        </nav>
    </header>

    <main>
        <!-- Hero Seksjon for ESG -->
        <section id="esg-hero" class="hero-esg">
            <div class="container">
                <h1 class="fade-in">Datadrevet ESG-Rapportering med Microsoft Fabric</h1>
                <div class="typing-container fade-in" style="animation-delay: 0.5s;">
                    <span id="typing-text-esg"></span><span class="typing-cursor"></span>
                </div>
                <div class="hero-cta-container">
                    <a href="#kontakt-esg" class="cta-button fade-in" style="animation-delay: 1s;">Start Din ESG-Reise Med Oss</a>
                </div>
            </div>
        </section>

        <!-- Hvorfor ESG Rapportering? -->
        <section id="hvorfor-esg" class="section">
             <div class="container">
                 <div class="section-header fade-in">
                     <span>Bærekraft i Fokus</span>
                     <h2>Hvorfor er ESG-Rapportering Viktig Nå?</h2>
                     <p>ESG (Environmental, Social, and Governance) er ikke lenger bare et "buzzword", men en kritisk komponent for moderne virksomheter. Økende regulatoriske krav (som EUs Taksonomi og CSRD), kombinert med forventninger fra investorer, kunder og ansatte, gjør robust ESG-rapportering essensielt.</p>
                     <p style="margin-top: 1rem;">God ESG-rapportering gir ikke bare compliance, men også innsikt for bedre beslutninger, styrket omdømme og økt konkurransekraft.</p>
                 </div>

                 <div class="key-benefits-grid">
                    <div class="benefit-item fade-in slide-left" style="transition-delay: 0.2s;">
                        <i class="fas fa-balance-scale"></i>
                        <h4>Regulatorisk Etterlevelse</h4>
                        <p>Møt komplekse krav fra EU og nasjonale myndigheter (CSRD, Taksonomi) på en effektiv måte.</p>
                    </div>
                    <div class="benefit-item fade-in" style="transition-delay: 0.4s;">
                        <i class="fas fa-chart-line"></i>
                        <h4>Forbedret Beslutningstaking</h4>
                        <p>Få dypere innsikt i din virksomhets bærekraftytelse for å identifisere risiko og muligheter.</p>
                    </div>
                    <div class="benefit-item fade-in slide-right" style="transition-delay: 0.6s;">
                        <i class="fas fa-shield-alt"></i>
                        <h4>Styrket Omdømme & Tillit</h4>
                        <p>Bygg tillit hos investorer, kunder og andre interessenter gjennom transparent og troverdig rapportering.</p>
                    </div>
                </div>
             </div>
         </section>

        <!-- Vår Tilnærming med Microsoft Fabric -->
        <section id="var-tilnaerming-esg" class="section services-bg">
            <div class="container">
                <div class="section-header fade-in">
                    <span>Vår Løsning</span>
                    <h2>Slik Hjelper TrendMe med ESG & Microsoft Fabric</h2>
                    <p>Vi kombinerer vår ekspertise innen Microsoft Fabric med en dyp forståelse for ESG-rapportering for å levere en helhetlig løsning. Microsoft Fabric tilbyr en unik, samlet plattform for å håndtere hele ESG-datareisen.</p>
                </div>
                <div class="service-grid">
                    <div class="service-card fade-in slide-left" style="transition-delay: 0.2s;">
                          <div class="service-icon-container">
                              <img src="https://res.cloudinary.com/dm2movu5v/image/upload/f_auto,q_auto/v1746189619/lakehouse_put05u.png" alt="ESG Datainnsamling Ikon" class="service-icon esg-icon">
                          </div>
                         <h3>Datainnsamling & Integrasjon i OneLake</h3>
                         <ul>
                             <li>Identifisering av relevante ESG-datakilder (energi, utslipp, sosiale data, governance-data).</li>
                             <li>Automatisert datainnhenting med Fabric Data Factory (Pipelines, Dataflows Gen2).</li>
                             <li>Strukturering og lagring av ESG-data i et sentralisert OneLake.</li>
                             <li>Sikring av datakvalitet og sporbarhet.</li>
                         </ul>
                     </div>
                     <div class="service-card fade-in" style="transition-delay: 0.4s;">
                          <div class="service-icon-container">
                              <img src="https://res.cloudinary.com/dm2movu5v/image/upload/f_auto,q_auto/v1746189662/powerbi_datamodellering_khn6sc.png" alt="ESG Analyse og KPI Ikon" class="service-icon esg-icon">
                          </div>
                         <h3>ESG Analyse, KPI-er & Datamodellering</h3>
                         <ul>
                             <li>Utvikling av ESG-datamodeller tilpasset standarder (f.eks. GRI, ESRS for CSRD).</li>
                             <li>Beregning av nøkkelindikatorer (KPI-er) for miljø, sosiale forhold og selskapsstyring.</li>
                             <li>Analyse av Scope 1, 2 og 3 karbonutslipp.</li>
                             <li>Avansert analyse med Fabric Spark Notebooks for dypere innsikt.</li>
                         </ul>
                     </div>
                     <div class="service-card fade-in slide-right" style="transition-delay: 0.6s;">
                          <div class="service-icon-container">
                              <img src="https://res.cloudinary.com/dm2movu5v/image/upload/f_auto,q_auto/v1746189652/powerbi_logo_s9snvf.png" alt="ESG Rapportering Power BI Ikon" class="service-icon pbi-logo">
                          </div>
                         <h3>Visualisering & Rapportering med Power BI</h3>
                         <ul>
                             <li>Interaktive Power BI-dashboards for ESG-oversikt og -ytelse.</li>
                             <li>Automatisert generering av data for lovpålagte ESG-rapporter.</li>
                             <li>Skreddersydde rapporter for interne og eksterne interessenter.</li>
                             <li>Bruk av DirectLake for sanntidsinnsikt i ESG-data fra OneLake.</li>
                         </ul>
                     </div>
                </div>
            </div>
        </section>

        <!-- Tjenesteprosessen (Valgfritt - Accordion) -->
        <section id="esg-prosess" class="section">
            <div class="container">
                <div class="section-header fade-in">
                    <span>Vår Prosess</span>
                    <h2>Fra Data til Bærekraftsrapport</h2>
                    <p>Vi følger en strukturert prosess for å sikre at din ESG-rapporteringsløsning blir vellykket og gir maksimal verdi.</p>
                </div>
                <div class="accordion-list fade-in" style="transition-delay: 0.3s;">
                    <div class="accordion-item">
                        <button class="accordion-title">
                            <span class="tittel-tekst">1. Behovsanalyse & Strategi</span>
                            <span class="ikon">+</span>
                        </button>
                        <div class="accordion-content">
                            <p>Vi starter med å forstå din virksomhets spesifikke ESG-mål, regulatoriske krav, eksisterende datakilder og rapporteringsbehov. Sammen definerer vi en klar strategi og et veikart for implementeringen.</p>
                            <ul>
                                <li>Kartlegging av interessenter og deres forventninger.</li>
                                <li>Identifisering av relevante ESG-rammeverk (CSRD, GRI, SASB, TCFD etc.).</li>
                                <li>Vurdering av datatilgjengelighet og -kvalitet.</li>
                            </ul>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <button class="accordion-title">
                             <span class="tittel-tekst">2. Løsningsdesign & Implementering i Fabric</span>
                             <span class="ikon">+</span>
                        </button>
                        <div class="accordion-content">
                            <p>Basert på strategien designer vi en skreddersydd ESG-dataløsning i Microsoft Fabric. Dette inkluderer oppsett av OneLake, dataintegrasjonsflyter, datamodeller for analyse, og definisjon av KPI-er.</p>
                             <ul>
                                 <li>Arkitektur for datainnsamling og lagring i OneLake.</li>
                                 <li>Konfigurasjon av Data Factory for ETL/ELT-prosesser.</li>
                                 <li>Utvikling av ESG-datamodell og beregningslogikk (SQL, Spark, DAX).</li>
                             </ul>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <button class="accordion-title">
                             <span class="tittel-tekst">3. Visualisering, Rapportering & Opplæring</span>
                             <span class="ikon">+</span>
                        </button>
                        <div class="accordion-content">
                            <p>Vi utvikler intuitive Power BI-dashboards og rapporter som gir deg full oversikt over din ESG-ytelse. Vi sørger også for grundig opplæring slik at ditt team kan utnytte løsningen fullt ut.</p>
                             <ul>
                                 <li>Design av interaktive dashboards og rapporter i Power BI.</li>
                                 <li>Oppsett av automatiserte dataflyter for rapportering.</li>
                                 <li>Opplæring av superbrukere og sluttbrukere.</li>
                                 <li>Etablering av prosesser for kontinuerlig forbedring og vedlikehold.</li>
                             </ul>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Kontakt Seksjon -->
        <section id="kontakt-esg" class="section services-bg"> <!-- Endret ID for å unngå konflikt hvis den inkluderes et sted -->
            <div class="container">
                 <div class="section-header fade-in">
                     <span>Klar for å Starte?</span>
                    <h2>Kontakt Oss for en ESG-Prat</h2>
                    <p>La oss hjelpe deg med å navigere kompleksiteten i ESG-rapportering og utnytte kraften i Microsoft Fabric for å bygge en robust og innsiktsfull løsning. Fyll ut skjemaet for en uforpliktende samtale.</p>
                </div>
                <form id="contact-form-esg" class="fade-in" style="transition-delay: 0.3s;"> <!-- Endret ID -->
                    <div class="form-group">
                        <label for="name-esg">Navn:</label>
                        <input type="text" id="name-esg" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email-esg">E-post:</label>
                        <input type="email" id="email-esg" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="company-esg">Bedrift:</label>
                        <input type="text" id="company-esg" name="company" required>
                        <!-- Du kan gjenbruke Brreg-søkelogikken her om ønskelig, husk å gi input og suggestions-container unike IDer -->
                    </div>
                     <div class="form-group">
                        <label for="phone-esg">Telefon (valgfritt):</label>
                        <input type="tel" id="phone-esg" name="phone">
                    </div>
                    <div class="form-group">
                        <label for="message-esg">Din Henvendelse (ESG):</label>
                        <textarea id="message-esg" name="message" rows="6" required placeholder="Fortell oss kort om dine ESG-utfordringer eller mål..."></textarea>
                    </div>
                    <button type="submit" class="cta-button">Be om ESG-Konsultasjon</button>
                    <p id="form-error-message-esg"></p> <!-- Endret ID -->
                </form>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <p>© <span id="year-esg"></span> TrendMe. Alle rettigheter reservert.</p>
            <p>Spesialister på Datadrevet ESG-Rapportering med Microsoft Fabric.</p>
		    <p>Org.nr.: 935 389 763</p>
            <div class="footer-links">
                <!-- Du kan legge til sosiale medier-lenker her om ønskelig, likt som på hovedsiden -->
             </div>
        </div>
    </footer>

    <!-- Animasjonscontainer for kontaktskjema (valgfritt) -->
    <div id="animation-container-esg">
        <div id="paper-esg"><pre id="paper-content-esg"></pre></div>
        <div id="thank-you-message-esg">Tusen takk! Vi tar kontakt snarest angående din ESG-henvendelse.</div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // --- Intersection Observer (lik som før) ---
            const observerOptions = { root: null, rootMargin: '0px', threshold: 0.1 };
            const observerCallback = (entries, obs) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        obs.unobserve(entry.target);
                    }
                });
            };
            const intersectionObserver = new IntersectionObserver(observerCallback, observerOptions);
            const elementsToAnimate = document.querySelectorAll('.fade-in, .slide-up, .slide-left, .slide-right');
            elementsToAnimate.forEach(el => {
                 if (el.classList.contains('slide-up') || el.classList.contains('slide-left') || el.classList.contains('slide-right')) {
                    if (!el.classList.contains('fade-in')) { el.classList.add('fade-in'); }
                 }
                intersectionObserver.observe(el);
            });

            // --- Smooth scrolling for internlenker på ESG-siden (hvis du har noen) ---
            const navLinksEsg = document.querySelectorAll('header nav a[href^="#"], .hero-esg a[href^="#"]'); // Inkluderer hero CTA
            const headerEsg = document.getElementById('main-header');
            navLinksEsg.forEach(link => {
                link.addEventListener('click', function(e) {
                    let targetId = this.getAttribute('href');
                    if (targetId && targetId.startsWith('#') && targetId.length > 1 && document.getElementById(targetId.substring(1))) { // Sjekk at elementet finnes på DENNE siden
                        e.preventDefault();
                        try {
                            let targetElement = document.querySelector(targetId);
                            if (targetElement) {
                                const headerOffset = headerEsg ? headerEsg.offsetHeight : 0;
                                const elementPosition = targetElement.getBoundingClientRect().top + window.pageYOffset;
                                const stickyHeaderOffset = (window.getComputedStyle(headerEsg).position === 'sticky' && headerEsg.getBoundingClientRect().top <= 0) ? headerOffset : 0;
                                const offsetPosition = elementPosition - stickyHeaderOffset - 20;
                                window.scrollTo({ top: offsetPosition, behavior: 'smooth' });
                            }
                        } catch (error) { console.error(`Error finding element for smooth scroll: ${targetId}`, error); }
                    } else if (targetId === '#esg-hero') { // For "Hjem"-lignende lenke på denne siden
                        e.preventDefault(); window.scrollTo({ top: 0, behavior: 'smooth' });
                    }
                    // Hvis lenken er til index.html#seksjon, la nettleseren håndtere det.
                });
            });


            // --- Skrivemaskineffekt for ESG-siden ---
            const typingTextElementEsg = document.getElementById('typing-text-esg');
            if (typingTextElementEsg) {
                const textToTypeEsg = "Bærekraft. Innsikt. Rapportering. Drevet av Data.";
                let charIndexEsg = 0;
                function typeCharEsg() {
                    if (charIndexEsg < textToTypeEsg.length) {
                        if (charIndexEsg === 0) typingTextElementEsg.textContent = '';
                        typingTextElementEsg.textContent += textToTypeEsg.charAt(charIndexEsg);
                        charIndexEsg++;
                        setTimeout(typeCharEsg, 70); // Litt raskere for undersider kanskje
                    }
                }
                setTimeout(typeCharEsg, 1800);
            }

            // --- Accordion Logikk (lik som før, men sjekk om elementer finnes) ---
            const accordionTitlesEsg = document.querySelectorAll('#esg-prosess .accordion-title');
            if (accordionTitlesEsg.length > 0) {
                accordionTitlesEsg.forEach(title => {
                    title.addEventListener('click', function() {
                        const parentItem = this.closest('.accordion-item');
                        if (!parentItem) return;
                        const content = parentItem.querySelector('.accordion-content');
                        const icon = this.querySelector('.ikon');
                        const isAlreadyActive = this.classList.contains('aktiv');
                        const parentList = this.closest('.accordion-list');

                        if (parentList) {
                            parentList.querySelectorAll('.accordion-item').forEach(otherItem => {
                                const otherTitle = otherItem.querySelector('.accordion-title');
                                const otherContent = otherItem.querySelector('.accordion-content');
                                if (otherTitle !== this && otherTitle.classList.contains('aktiv')) {
                                    otherTitle.classList.remove('aktiv');
                                    if (otherContent) { otherContent.style.maxHeight = null; otherContent.classList.remove('aktiv'); }
                                    const otherIcon = otherTitle.querySelector('.ikon');
                                    if (otherIcon) otherIcon.textContent = '+';
                                }
                            });
                        }

                        if (isAlreadyActive) {
                            this.classList.remove('aktiv');
                            if (content) { content.style.maxHeight = null; content.classList.remove('aktiv'); }
                            if (icon) icon.textContent = '+';
                        } else {
                            this.classList.add('aktiv');
                            if (content) {
                                content.classList.add('aktiv');
                                requestAnimationFrame(() => { content.style.maxHeight = content.scrollHeight + "px"; });
                            }
                            if (icon) icon.textContent = '−';
                        }
                    });
                });
            }


            // --- Footer årstall for ESG-siden ---
            const yearSpanEsg = document.getElementById('year-esg');
            if (yearSpanEsg) { yearSpanEsg.textContent = new Date().getFullYear(); }

            // === Kontaktskjema Animasjon & Formspree Submit for ESG-siden ===
            const contactFormEsg = document.getElementById('contact-form-esg');
            const animationContainerEsg = document.getElementById('animation-container-esg'); // Sørg for at disse ID-ene er unike hvis du har flere skjemaer
            const paperEsg = document.getElementById('paper-esg');
            const paperContentEsg = document.getElementById('paper-content-esg');
            const thankYouMessageEsg = document.getElementById('thank-you-message-esg');
            const nameInputEsg = document.getElementById('name-esg');
            const emailInputEsg = document.getElementById('email-esg');
            const companyInputEsg = document.getElementById('company-esg');
            const phoneInputEsg = document.getElementById('phone-esg');
            const messageInputEsg = document.getElementById('message-esg');
            const submitButtonEsg = contactFormEsg?.querySelector('button[type="submit"]');
            const formErrorMessageEsg = document.getElementById('form-error-message-esg');

            if (contactFormEsg && animationContainerEsg && paperEsg && paperContentEsg && thankYouMessageEsg && nameInputEsg && emailInputEsg && companyInputEsg && messageInputEsg && phoneInputEsg && submitButtonEsg && formErrorMessageEsg) {
                async function handleSubmitEsg(event) {
                    event.preventDefault();
                    const originalButtonText = submitButtonEsg.textContent;
                    submitButtonEsg.disabled = true;
                    submitButtonEsg.textContent = 'Sender...';
                    formErrorMessageEsg.style.display = 'none';

                    const formData = new FormData(contactFormEsg);
                    const formSpreeEndpoint = 'https://formspree.io/f/xyzenqnp'; // SAMME ENDPOINT? ELLER ET NYTT FOR ESG?

                    try {
                        const response = await fetch(formSpreeEndpoint, {
                            method: 'POST',
                            body: formData,
                            headers: { 'Accept': 'application/json' }
                        });

                        if (response.ok) {
                            const formDataText = `ESG Henvendelse:\nFra: ${nameInputEsg.value}\nE-post: ${emailInputEsg.value}\n` +
                                               (companyInputEsg.value ? `Bedrift: ${companyInputEsg.value}\n` : '') +
                                               (phoneInputEsg.value ? `Telefon: ${phoneInputEsg.value}\n` : '') +
                                               `\nMelding:\n--------------------------\n${messageInputEsg.value}`;
                            paperContentEsg.textContent = formDataText;
                            animationContainerEsg.style.display = 'flex';
                            setTimeout(() => { paperEsg.style.opacity = '1'; paperEsg.style.transform = 'scale(1)'; }, 100);
                            setTimeout(() => { thankYouMessageEsg.style.display = 'block'; thankYouMessageEsg.offsetHeight; thankYouMessageEsg.style.opacity = '1'; }, 800);
                            setTimeout(() => { paperEsg.classList.add('flying'); }, 2500);
                        } else {
                            const responseData = await response.json();
                            let errorMessageText = 'Kunne ikke sende meldingen.';
                            if (responseData && responseData.errors && responseData.errors.length > 0) {
                                errorMessageText = responseData.errors.map(error => error.message).join(', ');
                            } else if (response.status === 422) {
                                errorMessageText = 'Vennligst sjekk at alle feltene er korrekt utfylt.';
                            }
                            formErrorMessageEsg.textContent = errorMessageText;
                            formErrorMessageEsg.style.display = 'block';
                            submitButtonEsg.disabled = false;
                            submitButtonEsg.textContent = originalButtonText;
                        }
                    } catch (error) {
                        formErrorMessageEsg.textContent = 'En nettverksfeil oppstod. Prøv igjen.';
                        formErrorMessageEsg.style.display = 'block';
                        submitButtonEsg.disabled = false;
                        submitButtonEsg.textContent = originalButtonText;
                    }
                }
                contactFormEsg.addEventListener('submit', handleSubmitEsg);

                paperEsg.addEventListener('animationend', (event) => {
                    if (event.animationName === 'fly-away' && paperEsg.classList.contains('flying')) {
                        animationContainerEsg.style.display = 'none';
                        paperEsg.classList.remove('flying');
                        thankYouMessageEsg.style.display = 'none';
                        thankYouMessageEsg.style.opacity = '0';
                        paperEsg.style.opacity = '0';
                        paperEsg.style.transform = 'scale(0.8)';
                        paperContentEsg.textContent = '';
                        contactFormEsg.reset();
                        submitButtonEsg.disabled = false;
                        submitButtonEsg.textContent = 'Be om ESG-Konsultasjon';
                    }
                });
            }
        });
    </script>
</body>
</html>
