# Portafolio-Oscar
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Oscar Iván Solarte - Ciencia de Datos & IA Generativa</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: #0a0e27;
            color: white;
            overflow-x: hidden;
            line-height: 1.6;
        }

        #neural-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(135deg, #0a0e27 0%, #1a1a3e 50%, #2d1b69 100%);
        }

        .container {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: rgba(10, 14, 39, 0.3);
            backdrop-filter: blur(10px);
        }

        .hero-content {
            max-width: 800px;
            animation: fadeInUp 1s ease-out;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #64b5f6, #42a5f5, #1e88e5);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: glow 2s ease-in-out infinite alternate;
        }

        .hero h2 {
            font-size: 1.8rem;
            color: #90caf9;
            margin-bottom: 30px;
        }

        .contact-info {
            font-size: 1.2rem;
            color: #e3f2fd;
            margin-bottom: 40px;
        }

        .contact-info div {
            margin: 10px 0;
        }

        .nav-menu {
            position: fixed;
            top: 30px;
            right: 30px;
            z-index: 1000;
            display: flex;
            gap: 20px;
        }

        .nav-btn {
            padding: 12px 24px;
            background: rgba(100, 181, 246, 0.2);
            border: 2px solid #64b5f6;
            color: white;
            text-decoration: none;
            border-radius: 30px;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .nav-btn:hover {
            background: rgba(100, 181, 246, 0.4);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(100, 181, 246, 0.3);
        }

        .section {
            padding: 80px 0;
            background: rgba(10, 14, 39, 0.6);
            backdrop-filter: blur(15px);
            margin: 40px 0;
            border-radius: 20px;
            border: 1px solid rgba(100, 181, 246, 0.2);
        }

        .section h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            color: #64b5f6;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .service-card {
            background: rgba(26, 26, 62, 0.8);
            padding: 30px;
            border-radius: 15px;
            border: 1px solid rgba(100, 181, 246, 0.3);
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(100, 181, 246, 0.2);
            border-color: #64b5f6;
        }

        .service-card h3 {
            color: #90caf9;
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .project-card {
            background: rgba(26, 26, 62, 0.9);
            padding: 25px;
            border-radius: 15px;
            border: 1px solid rgba(100, 181, 246, 0.3);
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .project-card:hover {
            transform: scale(1.02);
            box-shadow: 0 15px 35px rgba(100, 181, 246, 0.2);
        }

        .project-card h3 {
            color: #64b5f6;
            margin-bottom: 15px;
            font-size: 1.3rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 15px;
        }

        .tech-tag {
            background: rgba(100, 181, 246, 0.2);
            color: #90caf9;
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
            border: 1px solid rgba(100, 181, 246, 0.3);
        }

        .cta-button {
            display: inline-block;
            padding: 15px 40px;
            background: linear-gradient(45deg, #1565c0, #1976d2, #1e88e5);
            color: white;
            text-decoration: none;
            border-radius: 30px;
            font-weight: bold;
            transition: all 0.3s ease;
            margin-top: 30px;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 35px rgba(30, 136, 229, 0.4);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes glow {
            from {
                text-shadow: 0 0 20px rgba(100, 181, 246, 0.5);
            }
            to {
                text-shadow: 0 0 30px rgba(100, 181, 246, 0.8), 0 0 40px rgba(100, 181, 246, 0.3);
            }
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .nav-menu {
                flex-direction: column;
                top: 20px;
                right: 20px;
            }
            
            .services-grid,
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <canvas id="neural-canvas"></canvas>

    <nav class="nav-menu">
        <a href="#servicios" class="nav-btn">Servicios</a>
        <a href="#proyectos" class="nav-btn">Proyectos</a>
        <a href="#contacto" class="nav-btn">Contacto</a>
    </nav>

    <section class="hero">
        <div class="hero-content">
            <h1>Oscar Iván Solarte</h1>
            <h2>Especialista en Ciencia de Datos & IA Generativa</h2>
            <div class="contact-info">
                <div>📱 3154013707</div>
                <div>📧 3154013707@gmail.com</div>
            </div>
            <a href="#servicios" class="cta-button">Explorar Servicios</a>
        </div>
    </section>

    <div class="container">
        <section id="servicios" class="section">
            <h2>Servicios Especializados</h2>
            <div class="services-grid">
                <div class="service-card">
                    <h3>🧠 Ciencia de Datos</h3>
                    <p>Análisis avanzado de datos, modelado predictivo, machine learning y estadística aplicada para transformar datos en insights accionables y valor empresarial.</p>
                </div>
                <div class="service-card">
                    <h3>🤖 Inteligencia Artificial Generativa</h3>
                    <p>Implementación de modelos de IA generativa, ChatBots inteligentes, automatización de procesos y soluciones personalizadas con LLMs.</p>
                </div>
                <div class="service-card">
                    <h3>📊 Visualización de Datos</h3>
                    <p>Dashboards interactivos, reportes automatizados y visualizaciones impactantes que comunican insights de manera efectiva.</p>
                </div>
                <div class="service-card">
                    <h3>🔍 Análisis Predictivo</h3>
                    <p>Modelos de forecasting, análisis de series temporales y predicción de tendencias para la toma de decisiones estratégicas.</p>
                </div>
                <div class="service-card">
                    <h3>🛠️ MLOps & Deployment</h3>
                    <p>Implementación y despliegue de modelos en producción, pipelines automatizados y monitoreo continuo de performance.</p>
                </div>
                <div class="service-card">
                    <h3>💡 Consultoría en IA</h3>
                    <p>Asesoramiento estratégico para la adopción de IA, evaluación de casos de uso y roadmaps de transformación digital.</p>
                </div>
            </div>
        </section>

        <section id="proyectos" class="section">
            <h2>Repositorio de Proyectos</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>Sistema de Recomendación Inteligente</h3>
                    <p>Modelo de machine learning para recomendaciones personalizadas usando collaborative filtering y deep learning, mejorando la experiencia del usuario en 40%.</p>
                    <div class="project-tech">
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">TensorFlow</span>
                        <span class="tech-tag">Pandas</span>
                        <span class="tech-tag">AWS</span>
                    </div>
                </div>
                <div class="project-card">
                    <h3>ChatBot con IA Generativa</h3>
                    <p>Asistente virtual inteligente con procesamiento de lenguaje natural, integrado con GPT-4 y fine-tuning personalizado para atención al cliente.</p>
                    <div class="project-tech">
                        <span class="tech-tag">OpenAI API</span>
                        <span class="tech-tag">LangChain</span>
                        <span class="tech-tag">FastAPI</span>
                        <span class="tech-tag">Docker</span>
                    </div>
                </div>
                <div class="project-card">
                    <h3>Análisis Predictivo de Ventas</h3>
                    <p>Dashboard interactivo con forecasting automático, análisis de tendencias y alertas inteligentes para optimización de inventario.</p>
                    <div class="project-tech">
                        <span class="tech-tag">Prophet</span>
                        <span class="tech-tag">Streamlit</span>
                        <span class="tech-tag">Plotly</span>
                        <span class="tech-tag">PostgreSQL</span>
                    </div>
                </div>
                <div class="project-card">
                    <h3>Computer Vision para Calidad</h3>
                    <p>Sistema automatizado de inspección visual usando redes neuronales convolucionales para detección de defectos en tiempo real.</p>
                    <div class="project-tech">
                        <span class="tech-tag">OpenCV</span>
                        <span class="tech-tag">PyTorch</span>
                        <span class="tech-tag">YOLO</span>
                        <span class="tech-tag">Flask</span>
                    </div>
                </div>
                <div class="project-card">
                    <h3>ETL Pipeline Automatizado</h3>
                    <p>Pipeline robusto de extracción, transformación y carga de datos con orquestación automática y monitoreo en tiempo real.</p>
                    <div class="project-tech">
                        <span class="tech-tag">Apache Airflow</span>
                        <span class="tech-tag">Spark</span>
                        <span class="tech-tag">Kafka</span>
                        <span class="tech-tag">MongoDB</span>
                    </div>
                </div>
                <div class="project-card">
                    <h3>Análisis de Sentimientos</h3>
                    <p>Herramienta de análisis de sentimientos en redes sociales con NLP avanzado y visualización en tiempo real de insights.</p>
                    <div class="project-tech">
                        <span class="tech-tag">NLTK</span>
                        <span class="tech-tag">spaCy</span>
                        <span class="tech-tag">React</span>
                        <span class="tech-tag">D3.js</span>
                    </div>
                </div>
            </div>
        </section>

        <section id="contacto" class="section">
            <h2>Contacto Profesional</h2>
            <div style="text-align: center; font-size: 1.2rem;">
                <p style="margin-bottom: 20px;">¿Listo para transformar tus datos en valor empresarial?</p>
                <div style="margin: 30px 0;">
                    <div style="margin: 15px 0;">
                        <strong>📱 Celular:</strong> 3154013707
                    </div>
                    <div style="margin: 15px 0;">
                        <strong>📧 Email:</strong> 3154013707@gmail.com
                    </div>
                </div>
                <a href="tel:3154013707" class="cta-button">Llamar Ahora</a>
                <a href="mailto:3154013707@gmail.com" class="cta-button" style="margin-left: 20px;">Enviar Email</a>
            </div>
        </section>
    </div>

    <script>
        // Neural Network 3D Animation
        class NeuralNetwork {
            constructor() {
                this.canvas = document.getElementById('neural-canvas');
                this.ctx = this.canvas.getContext('2d');
                this.nodes = [];
                this.connections = [];
                this.animationId = null;
                
                this.resize();
                this.init();
                this.animate();
                
                window.addEventListener('resize', () => this.resize());
            }
            
            resize() {
                this.canvas.width = window.innerWidth;
                this.canvas.height = window.innerHeight;
            }
            
            init() {
                this.nodes = [];
                this.connections = [];
                
                // Create nodes in multiple layers
                const layers = [
                    { count: 6, x: 0.1 },
                    { count: 8, x: 0.3 },
                    { count: 10, x: 0.5 },
                    { count: 8, x: 0.7 },
                    { count: 4, x: 0.9 }
                ];
                
                layers.forEach((layer, layerIndex) => {
                    for (let i = 0; i < layer.count; i++) {
                        this.nodes.push({
                            x: layer.x * this.canvas.width,
                            y: (i + 1) * this.canvas.height / (layer.count + 1),
                            z: Math.random() * 200 - 100,
                            originalZ: Math.random() * 200 - 100,
                            size: Math.random() * 4 + 2,
                            pulse: Math.random() * Math.PI * 2,
                            layer: layerIndex,
                            activation: 0
                        });
                    }
                });
                
                // Create connections between adjacent layers
                for (let i = 0; i < layers.length - 1; i++) {
                    const currentLayer = this.nodes.filter(node => node.layer === i);
                    const nextLayer = this.nodes.filter(node => node.layer === i + 1);
                    
                    currentLayer.forEach(startNode => {
                        nextLayer.forEach(endNode => {
                            if (Math.random() > 0.3) { // 70% connection probability
                                this.connections.push({
                                    start: startNode,
                                    end: endNode,
                                    weight: Math.random() * 2 - 1,
                                    activity: 0,
                                    pulse: Math.random() * Math.PI * 2
                                });
                            }
                        });
                    });
                }
            }
            
            animate() {
                this.ctx.fillStyle = 'rgba(10, 14, 39, 0.1)';
                this.ctx.fillRect(0, 0, this.canvas.width, this.canvas.height);
                
                const time = Date.now() * 0.001;
                
                // Update nodes
                this.nodes.forEach((node, index) => {
                    node.z = node.originalZ + Math.sin(time + node.pulse) * 50;
                    node.pulse += 0.02;
                    
                    // Simulate neural activation
                    node.activation = Math.sin(time + index * 0.1) * 0.5 + 0.5;
                });
                
                // Draw connections
                this.connections.forEach(conn => {
                    conn.activity = Math.sin(time + conn.pulse) * 0.5 + 0.5;
                    conn.pulse += 0.03;
                    
                    const startZ = 200 + conn.start.z;
                    const endZ = 200 + conn.end.z;
                    
                    const startScale = 200 / startZ;
                    const endScale = 200 / endZ;
                    
                    const startX = conn.start.x * startScale + this.canvas.width * (1 - startScale) / 2;
                    const startY = conn.start.y * startScale + this.canvas.height * (1 - startScale) / 2;
                    const endX = conn.end.x * endScale + this.canvas.width * (1 - endScale) / 2;
                    const endY = conn.end.y * endScale + this.canvas.height * (1 - endScale) / 2;
                    
                    const opacity = (conn.activity * 0.6 + 0.2) * Math.min(startScale, endScale);
                    const intensity = conn.activity;
                    
                    this.ctx.beginPath();
                    this.ctx.moveTo(startX, startY);
                    this.ctx.lineTo(endX, endY);
                    this.ctx.strokeStyle = `rgba(100, 181, 246, ${opacity})`;
                    this.ctx.lineWidth = intensity * 2 + 0.5;
                    this.ctx.stroke();
                    
                    // Animate data flow
                    if (conn.activity > 0.7) {
                        const progress = (Math.sin(time * 3 + conn.pulse) + 1) / 2;
                        const flowX = startX + (endX - startX) * progress;
                        const flowY = startY + (endY - startY) * progress;
                        
                        this.ctx.beginPath();
                        this.ctx.arc(flowX, flowY, 3, 0, Math.PI * 2);
                        this.ctx.fillStyle = `rgba(144, 202, 249, ${intensity})`;
                        this.ctx.fill();
                    }
                });
                
                // Draw nodes
                this.nodes.forEach(node => {
                    const z = 200 + node.z;
                    const scale = 200 / z;
                    
                    const x = node.x * scale + this.canvas.width * (1 - scale) / 2;
                    const y = node.y * scale + this.canvas.height * (1 - scale) / 2;
                    
                    const size = node.size * scale * (1 + node.activation * 0.5);
                    const opacity = scale * (0.6 + node.activation * 0.4);
                    
                    // Node core
                    this.ctx.beginPath();
                    this.ctx.arc(x, y, size, 0, Math.PI * 2);
                    this.ctx.fillStyle = `rgba(100, 181, 246, ${opacity})`;
                    this.ctx.fill();
                    
                    // Node glow
                    const gradient = this.ctx.createRadialGradient(x, y, 0, x, y, size * 3);
                    gradient.addColorStop(0, `rgba(144, 202, 249, ${opacity * 0.3})`);
                    gradient.addColorStop(1, 'rgba(144, 202, 249, 0)');
                    
                    this.ctx.beginPath();
                    this.ctx.arc(x, y, size * 3, 0, Math.PI * 2);
                    this.ctx.fillStyle = gradient;
                    this.ctx.fill();
                });
                
                this.animationId = requestAnimationFrame(() => this.animate());
            }
        }
        
        // Initialize neural network animation
        new NeuralNetwork();
        
        // Smooth scrolling for navigation
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
        
        // Add scroll-triggered animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeInUp 0.8s ease-out forwards';
                }
            });
        }, observerOptions);
        
        document.querySelectorAll('.service-card, .project-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            observer.observe(card);
        });
    </script>
</body>
</html>
