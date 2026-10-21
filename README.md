<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aprende Compu | Guía Práctica para la Prepa</title>
    <!-- Tailwind CSS desde CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Inter + Outfit para un toque fresco y juvenil -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Outfit:wght@600;800&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        heading: ['Outfit', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            word: '#2b579a',
                            excel: '#217346',
                            ppt: '#d24726',
                            security: '#6b21a8'
                        }
                    }
                }
            }
        }
    </script>
    <style>
        .active-tab {
            border-bottom: 3px solid #3b82f6;
            color: #1d4ed8;
            font-weight: 700;
        }
        .shortcut-key {
            background: #f1f5f9;
            border: 1px solid #cbd5e1;
            box-shadow: 0 2px 0 #94a3b8;
            border-radius: 4px;
            padding: 2px 6px;
            font-family: monospace;
            font-weight: bold;
            font-size: 0.85em;
            color: #334155;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans antialiased flex flex-col min-h-screen">

    <!-- Encabezado / Navegación principal -->
    <header class="bg-white border-b border-slate-200 sticky top-0 z-50">
        <div class="max-w-6xl mx-auto px-4 py-3 flex flex-wrap items-center justify-between gap-4">
            <div class="flex items-center gap-3 cursor-pointer" onclick="switchTab('inicio')">
                <div class="bg-blue-600 text-white font-heading font-extrabold text-xl p-2 rounded-xl shadow-md tracking-wider">
                    PC101
                </div>
                <div>
                    <h1 class="font-heading font-bold text-lg leading-none text-slate-900">Compu para la Prepa</h1>
                    <p class="text-xs text-slate-500 font-medium">Guía práctica sin rodeos</p>
                </div>
            </div>

            <!-- Menú Navegación -->
            <nav class="flex items-center gap-1 sm:gap-2 overflow-x-auto pb-1 sm:pb-0 w-full sm:w-auto">
                <button onclick="switchTab('word')" id="nav-word" class="tab-btn px-3 py-2 rounded-lg text-sm font-semibold text-slate-600 hover:bg-slate-100 flex items-center gap-2 transition">
                    <span class="w-3 h-3 rounded-full bg-blue-700"></span> Word
                </button>
                <button onclick="switchTab('excel')" id="nav-excel" class="tab-btn px-3 py-2 rounded-lg text-sm font-semibold text-slate-600 hover:bg-slate-100 flex items-center gap-2 transition">
                    <span class="w-3 h-3 rounded-full bg-emerald-600"></span> Excel
                </button>
                <button onclick="switchTab('ppt')" id="nav-ppt" class="tab-btn px-3 py-2 rounded-lg text-sm font-semibold text-slate-600 hover:bg-slate-100 flex items-center gap-2 transition">
                    <span class="w-3 h-3 rounded-full bg-orange-600"></span> PowerPoint
                </button>
                <button onclick="switchTab('seguridad')" id="nav-seguridad" class="tab-btn px-3 py-2 rounded-lg text-sm font-semibold text-slate-600 hover:bg-slate-100 flex items-center gap-2 transition">
                    <span class="w-3 h-3 rounded-full bg-purple-600"></span> Internet y Seguridad
                </button>
                <button onclick="switchTab('practica')" id="nav-practica" class="tab-btn px-3 py-2 rounded-lg text-sm font-bold bg-amber-100 text-amber-900 hover:bg-amber-200 ml-auto sm:ml-2 transition">
                    ⚡ Ponte a Prueba
                </button>
            </nav>
        </div>
    </header>

    <!-- Contenido Principal -->
    <main class="max-w-6xl mx-auto px-4 py-8 flex-grow w-full">

        <!-- VISTA: INICIO -->
        <section id="view-inicio" class="view-content space-y-8">
            <div class="bg-gradient-to-r from-blue-600 to-indigo-700 text-white rounded-3xl p-6 md:p-10 shadow-lg relative overflow-hidden">
                <div class="max-w-2xl relative z-10">
                    <span class="bg-blue-500/40 text-blue-100 text-xs font-semibold px-3 py-1 rounded-full uppercase tracking-wider inline-block mb-3">Guía de supervivencia escolar</span>
                    <h2 class="font-heading text-3xl sm:text-4xl font-extrabold mb-4 leading-tight">Sálvate en los trabajos de la prepa aprendiendo lo que de verdad usas.</h2>
                    <p class="text-blue-100 text-base mb-6 leading-relaxed">
                        Aquí no te enseñamos teoría aburrida del año 2000. Vas a aprender a dar formato a un ensayo APA en Word, armar tablas con formulas reales en Excel, hacer diapositivas geniales sin aburrir y no caer en estafas o virus.
                    </p>
                    <div class="flex flex-wrap gap-3">
                        <button onclick="switchTab('word')" class="bg-white text-blue-700 font-bold px-5 py-2.5 rounded-xl hover:bg-blue-50 transition shadow-sm">Empezar con Word</button>
                        <button onclick="switchTab('practica')" class="bg-blue-800/60 hover:bg-blue-800/80 text-white font-semibold px-5 py-2.5 rounded-xl border border-blue-400/30 transition">Probar lo que sabes</button>
                    </div>
                </div>
            </div>

            <!-- Atajos rápidos destacados -->
            <div class="bg-white rounded-2xl p-6 border border-slate-200 shadow-sm">
                <h3 class="font-heading font-bold text-xl text-slate-900 mb-4 flex items-center gap-2">
                    <span>🔥</span> Atajos de teclado que te ahorran horas
                </h3>
                <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-4">
                    <div class="p-3 bg-slate-50 rounded-xl border border-slate-200">
                        <p class="text-xs text-slate-500 font-semibold uppercase">Copiar y Pegar</p>
                        <p class="mt-1"><span class="shortcut-key">Ctrl</span> + <span class="shortcut-key">C</span> / <span class="shortcut-key">V</span></p>
                        <span class="text-xs text-slate-600">Básico para mover texto.</span>
                    </div>
                    <div class="p-3 bg-slate-50 rounded-xl border border-slate-200">
                        <p class="text-xs text-slate-500 font-semibold uppercase">Deshacer error</p>
                        <p class="mt-1"><span class="shortcut-key">Ctrl</span> + <span class="shortcut-key">Z</span></p>
                        <span class="text-xs text-slate-600">Salva vidas cuando borras algo por error.</span>
                    </div>
                    <div class="p-3 bg-slate-50 rounded-xl border border-slate-200">
                        <p class="text-xs text-slate-500 font-semibold uppercase">Buscar palabras</p>
                        <p class="mt-1"><span class="shortcut-key">Ctrl</span> + <span class="shortcut-key">B</span></p>
                        <span class="text-xs text-slate-600">Encuentra datos en documentos largos.</span>
                    </div>
                    <div class="p-3 bg-slate-50 rounded-xl border border-slate-200">
                        <p class="text-xs text-slate-500 font-semibold uppercase">Guardar rápido</p>
                        <p class="mt-1"><span class="shortcut-key">Ctrl</span> + <span class="shortcut-key">G</span></p>
                        <span class="text-xs text-slate-600">Guarda avances constantemente.</span>
                    </div>
                </div>
            </div>

            <!-- Módulos principales -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <!-- Tarjeta Word -->
                <div onclick="switchTab('word')" class="cursor-pointer bg-white p-6 rounded-2xl border-2 border-slate-200 hover:border-blue-500 transition shadow-sm hover:shadow-md group">
                    <div class="w-12 h-12 bg-blue-100 text-blue-700 rounded-xl flex items-center justify-center font-bold text-xl mb-4 group-hover:scale-110 transition-transform">W</div>
                    <h4 class="font-heading text-xl font-bold text-slate-900 mb-2">Microsoft Word</h4>
                    <p class="text-slate-600 text-sm mb-4">Aprende a estructurar un reporte con portada, índices automáticos, salto de página y formato legible.</p>
                    <span class="text-blue-600 font-semibold text-sm flex items-center gap-1 group-hover:translate-x-1 transition-transform">Ver lecciones &rarr;</span>
                </div>

                <!-- Tarjeta Excel -->
                <div onclick="switchTab('excel')" class="cursor-pointer bg-white p-6 rounded-2xl border-2 border-slate-200 hover:border-emerald-500 transition shadow-sm hover:shadow-md group">
                    <div class="w-12 h-12 bg-emerald-100 text-emerald-700 rounded-xl flex items-center justify-center font-bold text-xl mb-4 group-hover:scale-110 transition-transform">X</div>
                    <h4 class="font-heading text-xl font-bold text-slate-900 mb-2">Microsoft Excel</h4>
                    <p class="text-slate-600 text-sm mb-4">Pierde el miedo a las celdas. Fórmulas de suma, promedios para tus calificaciones y gráficas rápidas.</p>
                    <span class="text-emerald-600 font-semibold text-sm flex items-center gap-1 group-hover:translate-x-1 transition-transform">Ver lecciones &rarr;</span>
                </div>

                <!-- Tarjeta PPT -->
                <div onclick="switchTab('ppt')" class="cursor-pointer bg-white p-6 rounded-2xl border-2 border-slate-200 hover:border-orange-500 transition shadow-sm hover:shadow-md group">
                    <div class="w-12 h-12 bg-orange-100 text-orange-700 rounded-xl flex items-center justify-center font-bold text-xl mb-4 group-hover:scale-110 transition-transform">P</div>
                    <h4 class="font-heading text-xl font-bold text-slate-900 mb-2">PowerPoint</h4>
                    <p class="text-slate-600 text-sm mb-4">Crea presentaciones dinámicas. Menos texto, más impacto visual, reglas de contraste y animaciones discretas.</p>
                    <span class="text-orange-600 font-semibold text-sm flex items-center gap-1 group-hover:translate-x-1 transition-transform">Ver lecciones &rarr;</span>
                </div>

                <!-- Tarjeta Seguridad -->
                <div onclick="switchTab('seguridad')" class="cursor-pointer bg-white p-6 rounded-2xl border-2 border-slate-200 hover:border-purple-500 transition shadow-sm hover:shadow-md group">
                    <div class="w-12 h-12 bg-purple-100 text-purple-700 rounded-xl flex items-center justify-center font-bold text-xl mb-4 group-hover:scale-110 transition-transform">🛡️</div>
                    <h4 class="font-heading text-xl font-bold text-slate-900 mb-2">Internet y Seguridad</h4>
                    <p class="text-slate-600 text-sm mb-4">Cómo buscar fuentes confiables en Google, evitar phishing/virus y mantener tus contraseñas seguras.</p>
                    <span class="text-purple-600 font-semibold text-sm flex items-center gap-1 group-hover:translate-x-1 transition-transform">Ver lecciones &rarr;</span>
                </div>
            </div>
        </section>

        <!-- VISTA: WORD -->
        <section id="view-word" class="view-content hidden space-y-6">
            <div class="bg-blue-50 border border-blue-200 rounded-2xl p-6">
                <div class="flex items-center gap-3">
                    <span class="bg-blue-600 text-white font-bold text-xl px-3 py-1 rounded-lg">Word</span>
                    <div>
                        <h2 class="font-heading text-2xl font-bold text-blue-900">Documentos Impecables para la Prepa</h2>
                        <p class="text-blue-700 text-sm">Deja de presionar Enter 20 veces para pasar de página.</p>
                    </div>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <!-- Temario interactivo -->
                <div class="space-y-3">
                    <p class="font-bold text-slate-700 text-sm uppercase tracking-wider">Lecciones de Word</p>
                    <button onclick="loadLesson('word', 1)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-blue-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-blue-500">1. Saltos de Página vs Enter</button>
                    <button onclick="loadLesson('word', 2)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-blue-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-blue-500">2. Encabezados e Índices Automáticos</button>
                    <button onclick="loadLesson('word', 3)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-blue-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-blue-500">3. Interlineado y Formato Limpio</button>
                    <button onclick="loadLesson('word', 4)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-blue-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-blue-500">4. Exportar a PDF correctamente</button>
                </div>

                <!-- Detalle de lección -->
                <div class="md:col-span-2 bg-white border border-slate-200 rounded-2xl p-6 shadow-sm min-h-[300px]" id="word-lesson-display">
                    <!-- Se llena con JS -->
                </div>
            </div>
        </section>

        <!-- VISTA: EXCEL -->
        <section id="view-excel" class="view-content hidden space-y-6">
            <div class="bg-emerald-50 border border-emerald-200 rounded-2xl p-6">
                <div class="flex items-center gap-3">
                    <span class="bg-emerald-600 text-white font-bold text-xl px-3 py-1 rounded-lg">Excel</span>
                    <div>
                        <h2 class="font-heading text-2xl font-bold text-emerald-900">Excel Sin Miedo</h2>
                        <p class="text-emerald-700 text-sm">Organiza datos, saca tu promedio y crea gráficas sin quebrarte la cabeza.</p>
                    </div>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="space-y-3">
                    <p class="font-bold text-slate-700 text-sm uppercase tracking-wider">Lecciones de Excel</p>
                    <button onclick="loadLesson('excel', 1)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-emerald-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-emerald-500">1. ¿Qué es una Celda, Fila y Columna?</button>
                    <button onclick="loadLesson('excel', 2)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-emerald-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-emerald-500">2. Fórmula de Promedio y Suma</button>
                    <button onclick="loadLesson('excel', 3)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-emerald-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-emerald-500">3. Gráficas sencillas en 3 clics</button>
                </div>

                <div class="md:col-span-2 bg-white border border-slate-200 rounded-2xl p-6 shadow-sm min-h-[300px]" id="excel-lesson-display">
                    <!-- Se llena con JS -->
                </div>
            </div>
        </section>

        <!-- VISTA: POWERPOINT -->
        <section id="view-ppt" class="view-content hidden space-y-6">
            <div class="bg-orange-50 border border-orange-200 rounded-2xl p-6">
                <div class="flex items-center gap-3">
                    <span class="bg-orange-600 text-white font-bold text-xl px-3 py-1 rounded-lg">PPT</span>
                    <div>
                        <h2 class="font-heading text-2xl font-bold text-orange-900">Exposiciones de 10</h2>
                        <p class="text-orange-700 text-sm">Diseña diapositivas visuales que tus profesores sí quieran ver.</p>
                    </div>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="space-y-3">
                    <p class="font-bold text-slate-700 text-sm uppercase tracking-wider">Lecciones de PPT</p>
                    <button onclick="loadLesson('ppt', 1)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-orange-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-orange-500">1. La regla 6x6 (Menos texto)</button>
                    <button onclick="loadLesson('ppt', 2)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-orange-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-orange-500">2. Contraste de colores y fuentes</button>
                    <button onclick="loadLesson('ppt', 3)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-orange-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-orange-500">3. Animaciones discretas (Sin marear)</button>
                </div>

                <div class="md:col-span-2 bg-white border border-slate-200 rounded-2xl p-6 shadow-sm min-h-[300px]" id="ppt-lesson-display">
                    <!-- Se llena con JS -->
                </div>
            </div>
        </section>

        <!-- VISTA: SEGURIDAD -->
        <section id="view-seguridad" class="view-content hidden space-y-6">
            <div class="bg-purple-50 border border-purple-200 rounded-2xl p-6">
                <div class="flex items-center gap-3">
                    <span class="bg-purple-600 text-white font-bold text-xl px-3 py-1 rounded-lg">🛡️</span>
                    <div>
                        <h2 class="font-heading text-2xl font-bold text-purple-900">Navegación Inteligente y Segura</h2>
                        <p class="text-purple-700 text-sm">Busca información confiable para tus tareas y protege tu cuenta.</p>
                    </div>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="space-y-3">
                    <p class="font-bold text-slate-700 text-sm uppercase tracking-wider">Lecciones de Seguridad</p>
                    <button onclick="loadLesson('seguridad', 1)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-purple-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-purple-500">1. Cómo filtrar búsquedas en Google</button>
                    <button onclick="loadLesson('seguridad', 2)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-purple-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-purple-500">3. Identificar Phishing e hilos falsos</button>
                    <button onclick="loadLesson('seguridad', 3)" class="w-full text-left p-3 rounded-xl border border-slate-200 bg-white hover:border-purple-500 font-medium text-slate-800 text-sm transition focus:outline-none focus:ring-2 focus:ring-purple-500">2. Contraseñas fuertes y memorables</button>
                </div>

                <div class="md:col-span-2 bg-white border border-slate-200 rounded-2xl p-6 shadow-sm min-h-[300px]" id="seguridad-lesson-display">
                    <!-- Se llena con JS -->
                </div>
            </div>
        </section>

        <!-- VISTA: PRÁCTICA E INTERACTIVO -->
        <section id="view-practica" class="view-content hidden space-y-8">
            <div class="bg-amber-50 border border-amber-200 rounded-2xl p-6">
                <h2 class="font-heading text-2xl font-bold text-amber-900 mb-2">⚡ Zona Práctica: Simula y Ponte a Prueba</h2>
                <p class="text-amber-800 text-sm">Pon a prueba lo aprendido con este mini-quiz interactivo y la herramienta de promedios rápida.</p>
            </div>

            <!-- SIMULADOR RÁPIDO: CALCULADORA DE PROMEDIO EXCEL -->
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <h3 class="font-heading font-bold text-lg text-slate-900 mb-3 flex items-center gap-2">
                    <span class="text-emerald-600 font-bold">X</span> Mini-Simulador: Calcula tu Promedio Escolar
                </h3>
                <p class="text-slate-600 text-sm mb-4">Ingresa 3 calificaciones para simular la fórmula <code class="bg-slate-100 px-2 py-0.5 rounded text-emerald-700 font-mono text-xs">=PROMEDIO(A1:A3)</code> de Excel.</p>
                
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-4">
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">Materia 1</label>
                        <input type="number" id="grade1" value="8" min="0" max="10" class="w-full border border-slate-300 rounded-lg p-2 text-center font-bold text-slate-700 focus:ring-2 focus:ring-emerald-500 focus:outline-none">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">Materia 2</label>
                        <input type="number" id="grade2" value="9" min="0" max="10" class="w-full border border-slate-300 rounded-lg p-2 text-center font-bold text-slate-700 focus:ring-2 focus:ring-emerald-500 focus:outline-none">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-slate-600 mb-1">Materia 3</label>
                        <input type="number" id="grade3" value="10" min="0" max="10" class="w-full border border-slate-300 rounded-lg p-2 text-center font-bold text-slate-700 focus:ring-2 focus:ring-emerald-500 focus:outline-none">
                    </div>
                </div>
                <div class="flex items-center justify-between bg-slate-50 p-4 rounded-xl border border-slate-200">
                    <button onclick="calculateAverage()" class="bg-emerald-600 text-white font-bold px-4 py-2 rounded-lg hover:bg-emerald-700 transition text-sm">Ejecutar Fórmula</button>
                    <div class="text-right">
                        <span class="text-xs text-slate-500 font-medium">Resultado:</span>
                        <p id="average-result" class="text-xl font-extrabold text-emerald-700">9.0</p>
                    </div>
                </div>
            </div>

            <!-- QUIZ DE OPCIÓN MÚLTIPLE -->
            <div class="bg-white p-6 rounded-2xl border border-slate-200 shadow-sm">
                <div class="flex items-center justify-between mb-6">
                    <h3 class="font-heading font-bold text-lg text-slate-900">Quiz Rápido de Computación</h3>
                    <span id="quiz-score" class="text-xs font-bold bg-blue-100 text-blue-800 px-3 py-1 rounded-full">Puntos: 0</span>
                </div>

                <div id="quiz-container" class="space-y-6">
                    <!-- Las preguntas se inyectan con JS -->
                </div>
            </div>
        </section>

    </main>

    <!-- Pie de página sencillo -->
    <footer class="bg-white border-t border-slate-200 mt-auto py-6 text-center text-xs text-slate-500">
        <div class="max-w-6xl mx-auto px-4">
            <p class="font-medium text-slate-600">Material educativo diseñado para estudiantes de bachillerato y preparatoria.</p>
            <p class="mt-1">Sin complicaciones, directo al grano. ¡Aplica estos trucos en tu próxima tarea!</p>
        </div>
    </footer>

    <!-- LÓGICA JAVASCRIPT -->
    <script>
        // Datos de lecciones escritas de forma natural y clara
        const lessonsData = {
            word: {
                1: {
                    title: "1. Saltos de página vs presionar Enter varias veces",
                    content: `
                        <p class="text-slate-700 mb-4">Un error super común cuando entregamos un trabajo es presionar la tecla <span class="shortcut-key">Enter</span> diez veces para mandar un título a la siguiente página. Cuando agregas texto arriba, todo tu documento se desacomoda.</p>
                        <div class="bg-blue-50 border-l-4 border-blue-600 p-4 rounded-r-xl mb-4">
                            <h5 class="font-bold text-blue-900 text-sm">La solución correcta:</h5>
                            <p class="text-blue-800 text-sm mt-1">Usa la combinación <span class="shortcut-key">Ctrl</span> + <span class="shortcut-key">Enter</span>. Esto inserta un <strong>Salto de Página</strong> instantáneo. No importa qué agregues arriba, la siguiente página empezará justo donde querías.</p>
                        </div>
                    `
                },
                2: {
                    title: "2. Encabezados e Índices Automáticos",
                    content: `
                        <p class="text-slate-700 mb-4">No hagas un índice escribiendo puntos manualmente como <code>Introducción...........1</code>. Si cambia la página, tendrás que arreglar todo a mano.</p>
                        <ol class="list-decimal list-inside space-y-2 text-slate-700 text-sm mb-4">
                            <li>Selecciona tus títulos principales y aplícales el estilo <strong>Título 1</strong> o <strong>Título 2</strong> en la barra superior.</li>
                            <li>Ve a la pestaña <strong>Referencias</strong>.</li>
                            <li>Haz clic en <strong>Tabla de contenido</strong> y selecciona la primera opción.</li>
                        </ol>
                        <p class="text-xs text-slate-500 italic">¡Listo! Tu índice se genera solo y puedes actualizarlo con un solo clic si cambias algo.</p>
                    `
                },
                3: {
                    title: "3. Interlineado y Formato Limpio",
                    content: `
                        <p class="text-slate-700 mb-4">Para que un ensayo de la prepa luzca ordenado y profesional sin esfuerzo:</p>
                        <ul class="list-disc list-inside space-y-2 text-slate-700 text-sm mb-4">
                            <li><strong>Tipografía:</strong> Usa fuentes legibles como Arial, Calibri o Times New Roman a 11 o 12 puntos.</li>
                            <li><strong>Interlineado:</strong> Selecciona tu texto y presiona <span class="shortcut-key">Ctrl</span> + <span class="shortcut-key">2</span> para espacio doble, o usa 1.5 líneas en el menú de Párrafo.</li>
                            <li><strong>Alineación:</strong> Usa texto <strong>Justificado</strong> (<span class="shortcut-key">Ctrl</span> + <span class="shortcut-key">J</span>) para que los bordes laterales queden alineados.</li>
                        </ul>
                    `
                },
                4: {
                    title: "4. Guardar y Exportar a PDF",
                    content: `
                        <p class="text-slate-700 mb-4">Nunca envíes un trabajo en formato <code>.docx</code> a menos que el profe lo pida explícitamente, porque las imágenes y tipos de letra se pueden mover según la computadora donde se abra.</p>
                        <p class="text-slate-700 text-sm mb-4">Paso rápido: Ve a <strong>Archivo</strong> &rarr; <strong>Guardar como</strong> &rarr; Cambia el tipo de documento a <strong>PDF (*.pdf)</strong>. O simplemente usa <strong>Exportar a PDF</strong>.</p>
                    `
                }
            },
            excel: {
                1: {
                    title: "1. ¿Qué es una Celda, Fila y Columna?",
                    content: `
                        <p class="text-slate-700 mb-3">Excel se organiza en una cuadrícula sencilla:</p>
                        <ul class="list-disc list-inside space-y-2 text-slate-700 text-sm mb-4">
                            <li><strong>Columnas:</strong> Van verticales y se nombran con letras (A, B, C...).</li>
                            <li><strong>Filas:</strong> Van horizontales y se nombran con números (1, 2, 3...).</li>
                            <li><strong>Celda:</strong> Es la intersección de una columna y una fila. Por ejemplo, <strong>B4</strong> es la celda en columna B, fila 4.</li>
                        </ul>
                        <p class="text-xs text-emerald-800 bg-emerald-50 p-3 rounded-lg border border-emerald-200"><strong>Regla de oro:</strong> Toda fórmula en Excel DEBE empezar siempre con el signo igual <code>=</code>.</p>
                    `
                },
                2: {
                    title: "2. Fórmulas de Promedio y Suma",
                    content: `
                        <p class="text-slate-700 mb-3">Olvídate de sumar con la calculadora del celular e ingresar el dato manual.</p>
                        <div class="space-y-3">
                            <div class="p-3 bg-slate-50 rounded-lg border border-slate-200">
                                <p class="font-bold text-slate-800 text-sm">Suma automática:</p>
                                <code class="text-emerald-700 text-sm font-bold">=SUMA(A1:A10)</code>
                                <p class="text-xs text-slate-500 mt-1">Suma todos los números contenidos entre la celda A1 y la A10.</p>
                            </div>
                            <div class="p-3 bg-slate-50 rounded-lg border border-slate-200">
                                <p class="font-bold text-slate-800 text-sm">Promedio de calificaciones:</p>
                                <code class="text-emerald-700 text-sm font-bold">=PROMEDIO(B1:B5)</code>
                                <p class="text-xs text-slate-500 mt-1">Obtiene el promedio exacto sin tener que dividir manualmente entre la cantidad de materias.</p>
                            </div>
                        </div>
                    `
                },
                3: {
                    title: "3. Crear una gráfica en 3 clics",
                    content: `
                        <p class="text-slate-700 mb-4">Las gráficas hacen que cualquier reporte de ciencias o matemáticas se vea increíble.</p>
                        <ol class="list-decimal list-inside space-y-2 text-slate-700 text-sm mb-4">
                            <li>Selecciona la tabla con los datos que quieres graficar (incluyendo los títulos de la tabla).</li>
                            <li>Ve a la pestaña <strong>Insertar</strong>.</li>
                            <li>Elige <strong>Gráficos recomendados</strong> o selecciona una gráfica de barras/columnas sencilla.</li>
                        </ol>
                    `
                }
            },
            ppt: {
                1: {
                    title: "1. La regla 6x6 (Diapositivas limpias)",
                    content: `
                        <p class="text-slate-700 mb-3">El error más grande al exponer es llenar la diapositiva de párrafos gigantescos para leerlos directo del cañón.</p>
                        <div class="bg-orange-50 p-4 rounded-xl border border-orange-200 mb-3">
                            <h5 class="font-bold text-orange-900 text-sm">¿En qué consiste la regla 6x6?</h5>
                            <p class="text-orange-800 text-sm mt-1">Máximo <strong>6 líneas de texto</strong> por diapositiva y máximo <strong>6 palabras</strong> por cada línea. La diapositiva es un apoyo visual para tu público, no un acordeón personal.</p>
                        </div>
                    `
                },
                2: {
                    title: "2. Contraste de Colores y Tipografía",
                    content: `
                        <p class="text-slate-700 mb-3">Asegúrate de que tus textos se lean bien incluso si el cañón de la escuela proyecta con poca luz:</p>
                        <ul class="list-disc list-inside space-y-2 text-slate-700 text-sm mb-4">
                            <li><strong>Fondo claro + Texto oscuro:</strong> Ej. Fondo blanco o gris muy claro con texto azul marino o negro. (La opción más segura).</li>
                            <li><strong>Fondo oscuro + Texto claro:</strong> Ej. Fondo azul oscuro con texto blanco o amarillo claro.</li>
                            <li><strong>Evita:</strong> Combinar verde con rojo o usar letras fluorescentes que desgastan la vista.</li>
                        </ul>
                    `
                },
                3: {
                    title: "3. Animaciones discretas",
                    content: `
                        <p class="text-slate-700 mb-4">Las animaciones exageradas hacen perder tiempo y distraen a la clase.</p>
                        <p class="text-slate-700 text-sm mb-3">Usa efectos sencillos como <strong>Aparecer</strong> o <strong>Desvanecer</strong>. Evita efectos ruidosos o giros de 360 grados para cada elemento.</p>
                    `
                }
            },
            seguridad: {
                1: {
                    title: "1. Cómo filtrar búsquedas en Google",
                    content: `
                        <p class="text-slate-700 mb-3">Para encontrar mejores fuentes académicas y no quedarte solo con el primer resultado:</p>
                        <div class="space-y-2 text-sm">
                            <div class="p-2 bg-slate-50 border rounded font-mono">"Revolución Mexicana" PDF</div>
                            <p class="text-xs text-slate-500">Usa comillas para buscar la frase exacta y escribe "PDF" para hallar documentos o libros descargables.</p>
                            <div class="p-2 bg-slate-50 border rounded font-mono">site:.edu.mx célula vegetal</div>
                            <p class="text-xs text-slate-500">Usa <code>site:.edu</code> para limitar la búsqueda a portales educativos o universitarios de confianza.</p>
                        </div>
                    `
                },
                2: {
                    title: "2. Identificar Phishing e Hilos Falsos",
                    content: `
                        <p class="text-slate-700 mb-3">El <i>Phishing</i> es un engaño donde te mandan un mensaje simulando ser tu escuela, correo o red social para robarte la cuenta.</p>
                        <ul class="list-disc list-inside space-y-2 text-slate-700 text-sm mb-4">
                            <li>Revisa siempre la dirección o correo del remitente (ej. si dice <code>soporte@facebook-seguridad-alerta12.com</code> es falso).</li>
                            <li>Sospecha si te meten prisa ("¡Tu cuenta será cerrada en 2 horas!").</li>
                            <li>No des clic a enlaces sospechosos ni descargues archivos adjuntos extraños.</li>
                        </ul>
                    `
                },
                3: {
                    title: "3. Contraseñas fuertes y sencillas de recordar",
                    content: `
                        <p class="text-slate-700 mb-3">No uses <code>123456</code>, tu fecha de nacimiento ni tu nombre. Son las primeras que prueban los programas de rastreo.</p>
                        <div class="bg-purple-50 p-4 rounded-xl border border-purple-200">
                            <p class="font-bold text-purple-900 text-sm">Truco de la frase clave:</p>
                            <p class="text-purple-800 text-sm mt-1">Elige una frase que recuerdes bien y junta palabras con símbolos o números:</p>
                            <code class="block mt-2 bg-white p-2 rounded text-purple-900 font-bold border border-purple-300">MiPerritoLucas#2024!</code>
                        </div>
                    `
                }
            }
        };

        // Preguntas del Quiz
        const quizQuestions = [
            {
                q: "¿Cuál es el atajo de teclado para deshacer una acción cuando cometes un error?",
                options: ["Ctrl + C", "Ctrl + Z", "Ctrl + P", "Alt + F4"],
                correct: 1
            },
            {
                q: "¿Qué signo debe ir obligatoriamente al inicio de cualquier fórmula en Excel?",
                options: ["#", "$", "=", "%"],
                correct: 2
            },
            {
                q: "En Word, ¿cuál es la mejor manera de pasar el texto a la siguiente página sin desacomodar el documento?",
                options: [
                    "Presionar Enter diez veces",
                    "Usar la combinación Ctrl + Enter (Salto de página)",
                    "Cambiar el tamaño de la letra a 50pt",
                    "Borrar el texto y volverlo a escribir abajo"
                ],
                correct: 1
            },
            {
                q: "¿En qué consiste la regla de diseño 6x6 en PowerPoint?",
                options: [
                    "Usar 6 imágenes y 6 colores por diapositiva",
                    "Máximo 6 líneas de texto y 6 palabras por línea",
                    "Entregar la presentación en un grupo de 6 alumnos",
                    "Hacer diapositivas que duren 6 segundos"
                ],
                correct: 1
            },
            {
                q: "¿Cómo puedes restringir una búsqueda en Google para encontrar documentos en formato de archivo PDF?",
                options: [
                    "Escribiendo la palabra 'por favor'",
                    "Agregando la palabra PDF en la búsqueda o el comando filetype:pdf",
                    "Cerrando la ventana de Google y volviéndola a abrir",
                    "Haciendo clic derecho en cualquier enlace"
                ],
                correct: 1
            }
        ];

        let score = 0;

        // Función para cambiar de pestaña/módulo
        function switchTab(tabId) {
            // Ocultar todas las vistas
            document.querySelectorAll('.view-content').forEach(view => {
                view.classList.add('hidden');
            });

            // Remover estado activo de botones
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('bg-slate-100', 'text-blue-700', 'border-b-2', 'border-blue-600');
            });

            // Mostrar vista seleccionada
            const targetView = document.getElementById('view-' + tabId);
            if(targetView) {
                targetView.classList.remove('hidden');
            }

            // Marcar botón actual
            const targetNav = document.getElementById('nav-' + tabId);
            if(targetNav) {
                targetNav.classList.add('bg-slate-100', 'text-blue-700');
            }

            // Cargar lección 1 por defecto en cada módulo
            if(lessonsData[tabId]) {
                loadLesson(tabId, 1);
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Cargar contenido de lecciones
        function loadLesson(module, lessonId) {
            const display = document.getElementById(module + '-lesson-display');
            if (!display) return;

            const lesson = lessonsData[module][lessonId];
            if (lesson) {
                display.innerHTML = `
                    <h3 class="font-heading font-bold text-xl text-slate-900 mb-4 pb-2 border-b border-slate-100">${lesson.title}</h3>
                    <div class="prose prose-slate max-w-none">
                        ${lesson.content}
                    </div>
                `;
            }
        }

        // Simular promedio en Excel
        function calculateAverage() {
            const g1 = parseFloat(document.getElementById('grade1').value) || 0;
            const g2 = parseFloat(document.getElementById('grade2').value) || 0;
            const g3 = parseFloat(document.getElementById('grade3').value) || 0;

            const avg = (g1 + g2 + g3) / 3;
            document.getElementById('average-result').innerText = avg.toFixed(1);
        }

        // Cargar Quiz Interactivo
        function renderQuiz() {
            const container = document.getElementById('quiz-container');
            if(!container) return;

            container.innerHTML = '';
            score = 0;
            document.getElementById('quiz-score').innerText = 'Puntos: 0';

            quizQuestions.forEach((q, idx) => {
                const qCard = document.createElement('div');
                qCard.className = 'p-4 rounded-xl border border-slate-200 bg-slate-50 space-y-3';
                
                let optionsHTML = '';
                q.options.forEach((opt, optIdx) => {
                    optionsHTML += `
                        <label class="flex items-start gap-3 p-2.5 rounded-lg border border-slate-200 bg-white hover:bg-slate-100 cursor-pointer text-sm font-medium text-slate-700 transition">
                            <input type="radio" name="question-${idx}" value="${optIdx}" onchange="checkAnswer(${idx}, ${optIdx})" class="mt-0.5 text-blue-600 focus:ring-blue-500">
                            <span>${opt}</span>
                        </label>
                    `;
                });

                qCard.innerHTML = `
                    <p class="font-bold text-slate-800 text-sm">${idx + 1}. ${q.q}</p>
                    <div class="space-y-2" id="options-group-${idx}">
                        ${optionsHTML}
                    </div>
                    <p id="feedback-${idx}" class="text-xs font-bold hidden"></p>
                `;

                container.appendChild(qCard);
            });
        }

        // Evaluar respuesta del Quiz
        function checkAnswer(qIdx, selectedOpt) {
            const question = quizQuestions[qIdx];
            const feedback = document.getElementById(`feedback-${qIdx}`);
            const optionsGroup = document.getElementById(`options-group-${qIdx}`);

            if(!feedback || !optionsGroup) return;

            // Deshabilitar respuestas de esta pregunta
            const inputs = optionsGroup.querySelectorAll('input');
            inputs.forEach(input => input.disabled = true);

            if(selectedOpt === question.correct) {
                score += 10;
                feedback.innerText = '✨ ¡Correcto! Buen trabajo.';
                feedback.className = 'text-xs font-bold text-emerald-600 mt-2 block';
            } else {
                feedback.innerText = `❌ Ups, la opción correcta era: "${question.options[question.correct]}"`;
                feedback.className = 'text-xs font-bold text-rose-600 mt-2 block';
            }

            document.getElementById('quiz-score').innerText = `Puntos: ${score} / ${quizQuestions.length * 10}`;
        }

        // Inicialización al cargar página
        window.onload = function() {
            switchTab('inicio');
            renderQuiz();
        };
    </script>
</body>
</html>
