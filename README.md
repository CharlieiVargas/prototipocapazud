<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CTP Ing. Carlos Pascua Zúñiga</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.7;
            background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
            color: #2d3748;
            font-size: 16px;
        }

        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 2rem 1rem;
            text-align: center;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="50" cy="50" r="2" fill="rgba(255,255,255,0.1)"/></svg>') repeat;
            opacity: 0.3;
        }

        .header-content {
            position: relative;
            z-index: 1;
        }

        .header h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            font-weight: 700;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .header p {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            opacity: 0.95;
        }

        .header .subtitle {
            font-size: 1rem;
            opacity: 0.8;
            font-style: italic;
        }

        .nav-container {
            background: white;
            padding: 1rem;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .nav {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 0.5rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .nav-button {
            background: linear-gradient(135deg, #e2e8f0 0%, #cbd5e0 100%);
            border: none;
            padding: 1rem 2rem;
            border-radius: 12px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            color: #2d3748;
            transition: all 0.3s ease;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
            min-width: 140px;
        }

        .nav-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
            background: linear-gradient(135deg, #cbd5e0 0%, #a0aec0 100%);
        }

        .nav-button.active {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
        }

        .container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        .section {
            display: none;
            background: white;
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.1);
            margin-bottom: 2rem;
            border: 1px solid #e2e8f0;
        }

        .section.active {
            display: block;
            animation: fadeIn 0.5s ease-in-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section-title {
            color: #2d3748;
            font-size: 2.5rem;
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
            font-weight: 700;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 2px;
        }

        .highlight-box {
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
            padding: 2rem;
            border-radius: 15px;
            margin: 2rem 0;
            border-left: 5px solid #0ea5e9;
            box-shadow: 0 4px 15px rgba(14, 165, 233, 0.1);
        }

        .highlight-box h3 {
            color: #0c4a6e;
            font-size: 1.4rem;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .mission-vision {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            margin: 2rem 0;
        }

        .mission, .vision {
            background: linear-gradient(135deg, #fdf2f8 0%, #fce7f3 100%);
            padding: 2rem;
            border-radius: 15px;
            border-left: 5px solid #ec4899;
            box-shadow: 0 4px 15px rgba(236, 72, 153, 0.1);
        }

        .mission h3, .vision h3 {
            color: #be185d;
            font-size: 1.4rem;
            margin-bottom: 1rem;
        }

        .values-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }

        .value-card {
            background: linear-gradient(135deg, #f0fdf4 0%, #dcfce7 100%);
            padding: 1.5rem;
            border-radius: 12px;
            border-left: 4px solid #22c55e;
            box-shadow: 0 4px 12px rgba(34, 197, 94, 0.1);
        }

        .value-card h4 {
            color: #166534;
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .specialties-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }

        .specialty-card {
            background: linear-gradient(135deg, #fffbeb 0%, #fef3c7 100%);
            padding: 2rem;
            border-radius: 15px;
            border-top: 5px solid #f59e0b;
            box-shadow: 0 6px 20px rgba(245, 158, 11, 0.15);
            transition: all 0.3s ease;
        }

        .specialty-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(245, 158, 11, 0.2);
        }

        .specialty-card h3 {
            color: #92400e;
            font-size: 1.5rem;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .specialty-info {
            background: rgba(245, 158, 11, 0.1);
            padding: 0.8rem;
            border-radius: 8px;
            margin: 1rem 0;
            font-weight: 600;
            color: #92400e;
        }

        .specialty-field {
            background: rgba(14, 165, 233, 0.1);
            padding: 0.8rem;
            border-radius: 8px;
            margin-top: 1rem;
            color: #0c4a6e;
            font-weight: 600;
        }

        .regulations-grid {
            display: grid;
            gap: 2rem;
            margin: 2rem 0;
        }

        .regulation-card {
            background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
            padding: 2rem;
            border-radius: 15px;
            border-left: 5px solid #6366f1;
            box-shadow: 0 4px 15px rgba(99, 102, 241, 0.1);
        }

        .regulation-card h3 {
            color: #4338ca;
            font-size: 1.4rem;
            margin-bottom: 1.5rem;
        }

        .regulation-card ul {
            list-style: none;
        }

        .regulation-card li {
            margin-bottom: 0.8rem;
            padding-left: 1.5rem;
            position: relative;
        }

        .regulation-card li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #10b981;
            font-weight: bold;
            font-size: 1.2rem;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }

        .gallery-item {
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
            transition: all 0.3s ease;
        }

        .gallery-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .gallery-item img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }

        .contact-card {
            background: linear-gradient(135deg, #f3e8ff 0%, #e9d5ff 100%);
            padding: 2rem;
            border-radius: 15px;
            border-left: 5px solid #8b5cf6;
            box-shadow: 0 4px 15px rgba(139, 92, 246, 0.15);
        }

        .contact-card h3 {
            color: #6d28d9;
            font-size: 1.4rem;
            margin-bottom: 1rem;
        }

        .contact-info {
            background: rgba(139, 92, 246, 0.1);
            padding: 1.5rem;
            border-radius: 10px;
            margin: 1.5rem 0;
            color: #6d28d9;
        }

        @media (max-width: 768px) {
            .header h1 {
                font-size: 2rem;
            }
            
            .nav {
                flex-direction: column;
                align-items: center;
            }
            
            .nav-button {
                width: 100%;
                max-width: 300px;
            }
            
            .section {
                padding: 2rem 1.5rem;
            }
            
            .mission-vision {
                grid-template-columns: 1fr;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }

        .intro-text {
            font-size: 1.1rem;
            color: #4a5568;
            margin-bottom: 2rem;
            text-align: center;
            font-weight: 500;
        }

        .important-note {
            background: linear-gradient(135deg, #fef7cd 0%, #fef3c7 100%);
            padding: 1.5rem;
            border-radius: 12px;
            border-left: 5px solid #f59e0b;
            margin: 2rem 0;
            font-weight: 600;
            color: #92400e;
        }
    </style>
</head>
<body>
    <header class="header">
        <div class="header-content">
            <h1>CTP Ing. Carlos Pascua Zúñiga</h1>
            <p>Excelencia académica y formación técnica profesional</p>
            <p class="subtitle">Preparando a nuestros estudiantes para el éxito profesional y personal</p>
        </div>
    </header>

    <nav class="nav-container">
        <div class="nav">
            <button class="nav-button active" onclick="showSection('presentacion')">🏠 Presentación</button>
            <button class="nav-button" onclick="showSection('mision')">🎯 Misión y Visión</button>
            <button class="nav-button" onclick="showSection('especialidades')">📚 Especialidades</button>
            <button class="nav-button" onclick="showSection('normativas')">📋 Normativas</button>
            <button class="nav-button" onclick="showSection('galeria')">📸 Galería</button>
            <button class="nav-button" onclick="showSection('contacto')">📞 Contacto</button>
        </div>
    </nav>

    <div class="container">
        <!-- Sección Presentación -->
        <section id="presentacion" class="section active">
            <h2 class="section-title">NUESTRA INSTITUCIÓN</h2>
            
            <p class="intro-text">
                El Colegio Técnico Profesional Ingeniero Carlos Pascua Zúñiga es una institución educativa de excelencia que combina formación académica sólida con preparación técnica especializada, ofreciendo a nuestros estudiantes las herramientas necesarias para destacar en el competitivo mercado laboral actual.
            </p>

            <div class="highlight-box">
                <h3>🌟 ¿Por qué elegir educación técnica profesional?</h3>
                <p>Nuestros graduados obtienen certificaciones reconocidas por la industria, acceso directo al mundo laboral y la posibilidad de continuar estudios universitarios con una base sólida y práctica.</p>
            </div>

            <p style="font-size: 1.1rem; margin: 2rem 0;">
                Como institución comprometida con la formación integral, mantenemos estándares académicos rigurosos y un ambiente de respeto mutuo donde cada estudiante puede desarrollar su máximo potencial. Contamos con docentes especializados, infraestructura moderna y vínculos estrechos con el sector empresarial.
            </p>

            <div class="important-note">
                <strong>Compromiso familiar:</strong> Al elegir nuestra institución, las familias se integran a una comunidad educativa donde el éxito estudiantil es responsabilidad compartida entre colegio, estudiantes y padres de familia.
            </div>
        </section>

        <!-- Sección Misión y Visión -->
        <section id="mision" class="section">
            <h2 class="section-title">MISIÓN Y VISIÓN</h2>
            
            <div class="mission-vision">
                <div class="mission">
                    <h3>🎯 Nuestra Misión</h3>
                    <p>Somos una institución educativa pública comprometida con la excelencia académica y técnica, formando profesionales integrales con sólidos valores morales, espirituales y sociales. Preparamos a nuestros estudiantes para ser ciudadanos responsables, competitivos laboralmente y comprometidos con el desarrollo sostenible de Costa Rica.</p>
                </div>
                
                <div class="vision">
                    <h3>🌟 Nuestra Visión</h3>
                    <p>Ser reconocidos como la institución líder en educación técnica profesional de la región, formando graduados exitosos que contribuyan al desarrollo económico y social del país, con una educación integral que combine excelencia académica, competencias técnicas y valores humanos sólidos.</p>
                </div>
            </div>

            <h3 style="color: #2d3748; font-size: 1.8rem; margin: 3rem 0 2rem 0; text-align: center;">Valores del Colegio</h3>
            
            <div class="values-grid">
                <div class="value-card">
                    <h4>📖 Valores Formativos</h4>
                    <p>Disciplina, compromiso, orden, responsabilidad, puntualidad, esfuerzo y constancia.</p>
                </div>
                <div class="value-card">
                    <h4>💎 Valores Morales</h4>
                    <p>Honor, sinceridad, honestidad, verdad y respeto.</p>
                </div>
                <div class="value-card">
                    <h4>🙏 Valores Espirituales</h4>
                    <p>Justicia, amor, perdón y fe.</p>
                </div>
                <div class="value-card">
                    <h4>🤝 Valores Sociales</h4>
                    <p>Solidaridad, cooperación, tolerancia, cortesía, equidad, igualdad, convivencia e inclusión.</p>
                </div>
                <div class="value-card">
                    <h4>🌱 Valores Ambientales</h4>
                    <p>Protección, reciclaje, equilibrio y uso racional de los recursos naturales.</p>
                </div>
            </div>
        </section>

        <!-- Sección Especialidades -->
        <section id="especialidades" class="section">
            <h2 class="section-title">ESPECIALIDADES TÉCNICAS</h2>
            
            <p class="intro-text">
                Nuestras especialidades están diseñadas para preparar profesionales competentes con alta demanda en el mercado laboral costarricense. Cada programa incluye certificaciones industriales y prácticas profesionales.
            </p>

            <div class="specialties-grid">
                <div class="specialty-card">
                    <h3>💻 Desarrollo Web</h3>
                    <div class="specialty-info">
                        <strong>Duración:</strong> 3 años | <strong>Modalidad:</strong> Técnico Medio
                    </div>
                    <p>Programación moderna con HTML5, CSS3, JavaScript, bases de datos, desarrollo backend y frontend. Preparación para certificaciones internacionales en tecnologías web.</p>
                    <div class="specialty-field">
                        💼 Campo laboral: Empresas de software, desarrollo freelance, startups tecnológicas.
                    </div>
                </div>

                <div class="specialty-card">
                    <h3>🏦 Banca y Finanzas</h3>
                    <div class="specialty-info">
                        <strong>Duración:</strong> 3 años | <strong>Modalidad:</strong> Técnico Medio
                    </div>
                    <p>Operaciones bancarias, productos financieros, análisis de riesgo, atención al cliente y normativas del sistema financiero nacional.</p>
                    <div class="specialty-field">
                        💼 Campo laboral: Bancos, cooperativas, financieras, seguros.
                    </div>
                </div>

                <div class="specialty-card">
                    <h3>📊 Contabilidad</h3>
                    <div class="specialty-info">
                        <strong>Duración:</strong> 3 años | <strong>Modalidad:</strong> Técnico Medio
                    </div>
                    <p>Contabilidad general y avanzada, costos, auditoría, elaboración de estados financieros y manejo de software contable especializado.</p>
                    <div class="specialty-field">
                        💼 Campo laboral: Empresas públicas y privadas, despachos contables, consultoría.
                    </div>
                </div>

                <div class="specialty-card">
                    <h3>📋 Gestión Administrativa</h3>
                    <div class="specialty-info">
                        <strong>Duración:</strong> 3 años | <strong>Modalidad:</strong> Técnico Medio
                    </div>
                    <p>Administración empresarial, recursos humanos, gestión de proyectos, servicio al cliente y herramientas digitales para la gestión.</p>
                    <div class="specialty-field">
                        💼 Campo laboral: Oficinas administrativas, recursos humanos, gestión empresarial.
                    </div>
                </div>

                <div class="specialty-card">
                    <h3>🏗️ Construcción Civil</h3>
                    <div class="specialty-info">
                        <strong>Duración:</strong> 3 años | <strong>Modalidad:</strong> Técnico Medio
                    </div>
                    <p>Diseño arquitectónico, cálculos estructurales, lectura de planos, supervisión de obras y normativas de construcción vigentes.</p>
                    <div class="specialty-field">
                        💼 Campo laboral: Constructoras, supervisión de obras, diseño arquitectónico.
                    </div>
                </div>

                <div class="specialty-card">
                    <h3>🖊️ Dibujo Técnico</h3>
                    <div class="specialty-info">
                        <strong>Duración:</strong> 3 años | <strong>Modalidad:</strong> Técnico Medio
                    </div>
                    <p>Elaboración de planos técnicos, manejo de software CAD (AutoCAD, SolidWorks), representación gráfica y diseño industrial.</p>
                    <div class="specialty-field">
                        💼 Campo laboral: Empresas de diseño, industria manufacturera, consultoría técnica.
                    </div>
                </div>
            </div>
        </section>

        <!-- Sección Normativas -->
        <section id="normativas" class="section">
            <h2 class="section-title">NORMATIVAS Y REGLAMENTOS</h2>
            
            <p class="intro-text">
                Nuestras normativas garantizan un ambiente seguro, respetuoso y propicio para el aprendizaje. Estas reglas son fundamentales para mantener la excelencia académica y la convivencia armoniosa.
            </p>

            <div class="regulations-grid">
                <div class="regulation-card">
                    <h3>📋 Aspectos Académicos</h3>
                    <ul>
                        <li>Asistencia puntual obligatoria (mínimo 90% para aprobar)</li>
                        <li>Cumplimiento de tareas y proyectos en fechas establecidas</li>
                        <li>Participación activa en clases teóricas y prácticas</li>
                        <li>Respeto hacia docentes, compañeros y personal administrativo</li>
                    </ul>
                </div>

                <div class="regulation-card">
                    <h3>👔 Presentación Personal</h3>
                    <ul>
                        <li>Uso obligatorio del uniforme institucional completo</li>
                        <li>Presentación personal adecuada y limpia</li>
                        <li>Uso de carnet estudiantil visible durante toda la jornada</li>
                    </ul>
                </div>

                <div class="regulation-card">
                    <h3>📱 Uso de Tecnología</h3>
                    <ul>
                        <li>Dispositivos electrónicos solo con autorización docente</li>
                        <li>Uso responsable de internet y recursos digitales</li>
                        <li>Prohibido el uso de redes sociales durante clases</li>
                    </ul>
                </div>
            </div>

            <div class="important-note">
                <strong>Importante:</strong> Las familias que eligen nuestra institución se comprometen a apoyar y respetar estas normativas, colaborando activamente en la formación integral de sus hijos.
            </div>
        </section>

        <!-- Sección Galería -->
        <section id="galeria" class="section">
            <h2 class="section-title">NUESTRAS INSTALACIONES</h2>
            
            <p class="intro-text">
                Conozca las modernas instalaciones donde sus hijos desarrollarán sus competencias técnicas y académicas en un ambiente seguro y propicio para el aprendizaje.
            </p>

            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="https://scontent.flio1-1.fna.fbcdn.net/v/t39.30808-6/511065868_1255831762995701_1411123629451259992_n.jpg?stp=cp6_dst-jpegr_tt6&_nc_cat=107&ccb=1-7&_nc_sid=833d8c&_nc_ohc=ryj34oBiY3EQ7kNvwHHw0ZX&_nc_oc=Adl7mwPk5BYoic-8b5JTyebn-aImeV4sShllAyso8vtjhxcQMYaDNyROuIcnfviYgOw&_nc_zt=23&se=-1&_nc_ht=scontent.flio1-1.fna&_nc_gid=Ox35Gb81KhmsH_LjqmNhnQ&oh=00_AfafLEQcTORjhIMeh7cg-u97Wk8sTyz9mRmXGh6gYAfe6w&oe=68DB9647" alt="Instalaciones del colegio técnico profesional">
                </div>
                <div class="gallery-item">
                    <img src="https://scontent.flio1-1.fna.fbcdn.net/v/t39.30808-6/362259975_793083892603826_6377606679620257725_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=6ee11a&_nc_ohc=Wj4tjwYL54AQ7kNvwFpreXI&_nc_oc=AdnvY-sC67_wArVWb9YWC0irydo2d6b4lE6qacUlk-nJ
