<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Computación Básica para Prepa | Guía Interactiva</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            50: '#f0f9ff',
                            100: '#e0f2fe',
                            500: '#0284c7',
                            600: '#0284c7',
                            700: '#0369a1',
                            800: '#075985',
                            900: '#0c4a6e',
                        }
                    }
                }
            }
        }
    </script>
    <style>
        .no-scrollbar::-webkit-scrollbar { display: none; }
        .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
        .tab-btn.active {
            background-color: #0284c7;
            color: #ffffff;
            border-color: #0284c7;
            box-shadow: 0 4px 6px -1px rgba(2, 132, 199, 0.3);
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 font-sans antialiased min-h-screen flex flex-col">

    <!-- Header Navigation Bar -->
    <header class="bg-slate-900 text-white sticky top-0 z-50 shadow-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center gap-3 cursor-pointer" onclick="switchTab('word')">
                    <div class="bg-sky-500 p-2 rounded-xl text-white">
                        <i class="fa-solid fa-laptop-code text-xl"></i>
                    </div>
                    <div>
                        <span class="font-extrabold text-lg sm:text-xl tracking-tight text-white block leading-none">CompuPrepa</span>
                        <span class="text-xs text-sky-400 font-medium">Guía Definitiva de Computación</span>
                    </div>
                </div>
                <div class="hidden md:flex items-center space-x-3 text-xs sm:text-sm font-medium">
                    <button onclick="switchTab('quiz')" class="bg-amber-500 hover:bg-amber-600 text-slate-900 font-bold px-4 py-2 rounded-lg transition-all shadow-sm hover:shadow flex items-center gap-2">
                        <i class="fa-solid fa-square-check text-base"></i>
                        <span>Quiz Final</span>
                    </button>
                    <button onclick="switchTab('atajos')" class="bg-slate-800 hover:bg-slate-700 text-slate-200 px-3 py-2 rounded-lg transition-all flex items-center gap-2 border border-slate-700">
                        <i class="fa-solid fa-keyboard text-sky-400"></i>
                        <span>Atajos</span>
                    </button>
                </div>
            </div>
        </div>

        <!-- Scrollable Module Navigation Tabs -->
        <nav class="bg-slate-800 border-t border-slate-700/60 px-2 sm:px-4">
            <div class="max-w-7xl mx-auto flex space-x-1 sm:space-x-2 overflow-x-auto py-2 no-scrollbar text-xs sm:text-sm font-medium">
                <button onclick="switchTab('word')" id="btn-word" class="tab-btn active shrink-0 px-3 py-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-700 transition flex items-center gap-2 border border-transparent">
                    <i class="fa-regular fa-file-word text-blue-400"></i> Word
                </button>
                <button onclick="switchTab('excel')" id="btn-excel" class="tab-btn shrink-0 px-3 py-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-700 transition flex items-center gap-2 border border-transparent">
                    <i class="fa-regular fa-file-excel text-emerald-400"></i> Excel
                </button>
                <button onclick="switchTab('powerpoint')" id="btn-powerpoint" class="tab-btn shrink-0 px-3 py-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-700 transition flex items-center gap-2 border border-transparent">
                    <i class="fa-regular fa-file-powerpoint text-orange-400"></i> PowerPoint
                </button>
                <button onclick="switchTab('seguridad')" id="btn-seguridad" class="tab-btn shrink-0 px-3 py-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-700 transition flex items-center gap-2 border border-transparent">
                    <i class="fa-solid fa-shield-halved text-rose-400"></i> Seguridad & Web
                </button>
                <button onclick="switchTab('nube')" id="btn-nube" class="tab-btn shrink-0 px-3 py-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-700 transition flex items-center gap-2 border border-transparent">
                    <i class="fa-solid fa-cloud text-indigo-400"></i> Nube & Trabajo
                </button>
                <button onclick="switchTab('soporte')" id="btn-soporte" class="tab-btn shrink-0 px-3 py-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-700 transition flex items-center gap-2 border border-transparent">
                    <i class="fa-solid fa-wrench text-amber-400"></i> Soporte Técnico
                </button>
                <button onclick="switchTab('atajos')" id="btn-atajos" class="tab-btn shrink-0 px-3 py-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-700 transition flex items-center gap-2 border border-transparent">
                    <i class="fa-solid fa-bolt text-yellow-400"></i> Atajos
                </button>
                <button onclick="switchTab('recursos')" id="btn-recursos" class="tab-btn shrink-0 px-3 py-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-700 transition flex items-center gap-2 border border-transparent">
                    <i class="fa-solid fa-cubes text-teal-400"></i> Recursos
                </button>
                <button onclick="switchTab('faq')" id="btn-faq" class="tab-btn shrink-0 px-3 py-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-700 transition flex items-center gap-2 border border-transparent">
                    <i class="fa-solid fa-circle-question text-purple-400"></i> FAQ
                </button>
                <button onclick="switchTab('quiz')" id="btn-quiz" class="tab-btn shrink-0 px-3 py-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-700 transition flex items-center gap-2 border border-transparent">
                    <i class="fa-solid fa-graduation-cap text-amber-400"></i> Quiz Ampliado
                </button>
            </div>
        </nav>
    </header>

    <!-- Main Content Area -->
    <main class="flex-grow max-w-7xl w-full mx-auto p-4 sm:p-6 lg:p-8">

        <!-- MODULE 1: WORD -->
        <section id="tab-word" class="tab-content block space-y-6">
            <div class="bg-white rounded-2xl p-6 sm:p-8 border border-slate-200 shadow-sm">
                <div class="flex items-center gap-4 mb-6">
                    <div class="w-12 h-12 bg-blue-100 text-blue-600 rounded-xl flex items-center justify-center text-2xl font-bold">
                        <i class="fa-solid fa-file-lines"></i>
                    </div>
                    <div>
                        <h1 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Microsoft Word y Formato de Documentos</h1>
                        <p class="text-slate-600 text-sm sm:text-base">Aprende a estructurar proyectos académicos con calidad profesional y sin dolores de cabeza.</p>
                    </div>
                </div>

                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Apa Rules Card -->
                    <div class="bg-blue-50/60 rounded-xl p-5 border border-blue-100 space-y-3">
                        <h2 class="text-lg font-bold text-blue-900 flex items-center gap-2">
                            <i class="fa-solid fa-book-bookmark text-blue-600"></i> Normas APA 7.ª Edición (Lo Esencial)
                        </h2>
                        <p class="text-xs text-slate-600">Las reglas que todos los profesores de prepa te van a pedir para ensayos y reportes:</p>
                        <ul class="text-xs sm:text-sm text-slate-700 space-y-2">
                            <li class="flex items-start gap-2"><i class="fa-solid fa-check text-blue-500 mt-1"></i> <span><strong>Márgenes:</strong> 2.54 cm (1 pulgada) por todos los lados.</span></li>
                            <li class="flex items-start gap-2"><i class="fa-solid fa-check text-blue-500 mt-1"></i> <span><strong>Tipografía:</strong> Times New Roman 12pt, Arial 11pt o Calibri 11pt.</span></li>
                            <li class="flex items-start gap-2"><i class="fa-solid fa-check text-blue-500 mt-1"></i> <span><strong>Interlineado:</strong> 2.0 (Doble espacio) en todo el documento, sin espacio entre párrafos.</span></li>
                            <li class="flex items-start gap-2"><i class="fa-solid fa-check text-blue-500 mt-1"></i> <span><strong>Alineación:</strong> Izquierda (no justificado para APA estricto, aunque algunos profes piden justificado).</span></li>
                            <li class="flex items-start gap-2"><i class="fa-solid fa-check text-blue-500 mt-1"></i> <span><strong>Sangría:</strong> En la primera línea de cada párrafo (1.27 cm / Tabulador).</span></li>
                        </ul>
                    </div>

                    <!-- Index & Headings -->
                    <div class="bg-slate-50 rounded-xl p-5 border border-slate-200 space-y-3">
                        <h2 class="text-lg font-bold text-slate-900 flex items-center gap-2">
                            <i class="fa-solid fa-list-ol text-blue-600"></i> Tablas de Contenido Automáticas
                        </h2>
                        <p class="text-xs sm:text-sm text-slate-600">¡Olvídate de hacer el índice a mano poniendo puntitos!</p>
                        <ol class="text-xs sm:text-sm text-slate-700 space-y-2 list-decimal list-inside">
                            <li>Aplica estilos a tus títulos: selecciona el texto y marca como <strong>Título 1</strong> (para temas principales) o <strong>Título 2</strong> (subtemas) en la pestaña Inicio.</li>
                            <li>Ve al lugar donde quieras poner el índice (usualmente la página 2).</li>
                            <li>Dirígete a <strong>Referencias > Tabla de contenido</strong> y elige el modelo automático.</li>
                            <li>Si agregas más contenido, haz clic en <em>"Actualizar tabla"</em> y todo se reajustará solo.</li>
                        </ol>
                    </div>
                </div>

                <!-- Section Breaks & Headers -->
                <div class="mt-6 grid md:grid-cols-3 gap-4">
                    <div class="p-4 rounded-xl border border-slate-200 bg-white shadow-xs space-y-2">
                        <div class="text-sky-600 font-bold text-sm flex items-center gap-2">
                            <i class="fa-solid fa-scissors"></i> Saltos de Sección
                        </div>
                        <p class="text-xs text-slate-600">Te permiten tener páginas horizontales y verticales en el mismo documento o cambiar encabezados en capítulos diferentes. Usa <strong>Disposición > Saltos > Página siguiente</strong>.</p>
                    </div>

                    <div class="p-4 rounded-xl border border-slate-200 bg-white shadow-xs space-y-2">
                        <div class="text-sky-600 font-bold text-sm flex items-center gap-2">
                            <i class="fa-solid fa-heading"></i> Encabezados y Números
                        </div>
                        <p class="text-xs text-slate-600">Para omitir la portada del conteo, haz doble clic en el encabezado de la página 2 y activa la opción <strong>"Primera página diferente"</strong> o desvincula la sección anterior.</p>
                    </div>

                    <div class="p-4 rounded-xl border border-slate-200 bg-white shadow-xs space-y-2">
                        <div class="text-sky-600 font-bold text-sm flex items-center gap-2">
                            <i class="fa-solid fa-asterisk"></i> Notas al Pie vs Citas
                        </div>
                        <p class="text-xs text-slate-600">Usa <strong>Referencias > Insertar nota al pie</strong> para aclaraciones o definiciones rápidas abajo en la misma página sin interrumpir la lectura principal.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- MODULE 2: EXCEL -->
        <section id="tab-excel" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-2xl p-6 sm:p-8 border border-slate-200 shadow-sm">
                <div class="flex items-center gap-4 mb-6">
                    <div class="w-12 h-12 bg-emerald-100 text-emerald-600 rounded-xl flex items-center justify-center text-2xl font-bold">
                        <i class="fa-solid fa-table"></i>
                    </div>
                    <div>
                        <h1 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Microsoft Excel y Hoja de Cálculo</h1>
                        <p class="text-slate-600 text-sm sm:text-base">Domina celdas, fórmulas, gráficos e interpreta datos como todo un experto.</p>
                    </div>
                </div>

                <!-- Formulas Quick Cards -->
                <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4 mb-8">
                    <div class="p-4 rounded-xl bg-emerald-50/50 border border-emerald-200">
                        <div class="font-mono text-xs text-emerald-800 font-bold bg-emerald-200/60 inline-block px-2 py-0.5 rounded mb-2">=SUMA(A1:A10)</div>
                        <h2 class="font-semibold text-sm text-slate-900">Suma Automática</h2>
                        <p class="text-xs text-slate-600 mt-1">Suma todos los valores numéricos dentro del rango especificado en segundos.</p>
                    </div>
                    <div class="p-4 rounded-xl bg-emerald-50/50 border border-emerald-200">
                        <div class="font-mono text-xs text-emerald-800 font-bold bg-emerald-200/60 inline-block px-2 py-0.5 rounded mb-2">=PROMEDIO(B1:B5)</div>
                        <h2 class="font-semibold text-sm text-slate-900">Promedio / Media</h2>
                        <p class="text-xs text-slate-600 mt-1">Calcula la media aritmética. Ideal para obtener tus calificaciones del parcial.</p>
                    </div>
                    <div class="p-4 rounded-xl bg-emerald-50/50 border border-emerald-200">
                        <div class="font-mono text-xs text-emerald-800 font-bold bg-emerald-200/60 inline-block px-2 py-0.5 rounded mb-2">=CONTAR.SI(C1:C20, ">6")</div>
                        <h2 class="font-semibold text-sm text-slate-900">Conteo Condicional</h2>
                        <p class="text-xs text-slate-600 mt-1">Cuenta únicamente las celdas que cumplen con un criterio específico (ej. aprobados).</p>
                    </div>
                    <div class="p-4 rounded-xl bg-emerald-50/50 border border-emerald-200">
                        <div class="font-mono text-xs text-emerald-800 font-bold bg-emerald-200/60 inline-block px-2 py-0.5 rounded mb-2">=SI(A1>=6, "Aprobado", "Reprobado")</div>
                        <h2 class="font-semibold text-sm text-slate-900">Lógica Condicional</h2>
                        <p class="text-xs text-slate-600 mt-1">Evalúa una regla y devuelve un valor distinto según si se cumple o no.</p>
                    </div>
                    <div class="p-4 rounded-xl bg-emerald-50/50 border border-emerald-200">
                        <div class="font-mono text-xs text-emerald-800 font-bold bg-emerald-200/60 inline-block px-2 py-0.5 rounded mb-2">=BUSCARV("Juan", A1:D10, 3, FALSO)</div>
                        <h2 class="font-semibold text-sm text-slate-900">Búsqueda Vertical</h2>
                        <p class="text-xs text-slate-600 mt-1">Busca un dato en la primera columna y devuelve un valor en la misma fila.</p>
                    </div>
                    <div class="p-4 rounded-xl bg-emerald-50/50 border border-emerald-200">
                        <div class="font-mono text-xs text-emerald-800 font-bold bg-emerald-200/60 inline-block px-2 py-0.5 rounded mb-2">Tablas Dinámicas</div>
                        <h2 class="font-semibold text-sm text-slate-900">Resumen de Datos</h2>
                        <p class="text-xs text-slate-600 mt-1">Permite agrupar miles de datos en 2 clics para analizar promedios o totales por categoría.</p>
                    </div>
                </div>

                <!-- Interactive Grade Simulator -->
                <div class="bg-slate-900 text-white rounded-2xl p-6 shadow-md space-y-4">
                    <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center border-b border-slate-800 pb-4 gap-2">
                        <div>
                            <h2 class="text-lg font-bold text-emerald-400 flex items-center gap-2">
                                <i class="fa-solid fa-calculator"></i> Simulador Interactivo de Calificaciones de Prepa
                            </h2>
                            <p class="text-xs text-slate-400">Prueba cómo las fórmulas de Excel evalúan si apruebas o te vas a examen extraordinario.</p>
                        </div>
                        <button onclick="resetGradeSim()" class="text-xs bg-slate-800 hover:bg-slate-700 text-slate-300 px-3 py-1.5 rounded transition">
                            <i class="fa-solid fa-rotate-left"></i> Reiniciar
                        </button>
                    </div>

                    <div class="grid md:grid-cols-3 gap-6">
                        <!-- Inputs -->
                        <div class="space-y-3">
                            <label class="block text-xs font-medium text-slate-300">
                                Examen Parcial (40%): <span id="val-p1" class="text-emerald-400 font-bold">8.0</span>
                                <input type="range" id="sim-p1" min="0" max="10" step="0.5" value="8" oninput="calcGrades()" class="w-full mt-1 accent-emerald-500">
                            </label>
                            <label class="block text-xs font-medium text-slate-300">
                                Proyectos / Tareas (40%): <span id="val-p2" class="text-emerald-400 font-bold">9.0</span>
                                <input type="range" id="sim-p2" min="0" max="10" step="0.5" value="9" oninput="calcGrades()" class="w-full mt-1 accent-emerald-500">
                            </label>
                            <label class="block text-xs font-medium text-slate-300">
                                Participación / Asistencia (20%): <span id="val-p3" class="text-emerald-400 font-bold">7.0</span>
                                <input type="range" id="sim-p3" min="0" max="10" step="0.5" value="7" oninput="calcGrades()" class="w-full mt-1 accent-emerald-500">
                            </label>
                        </div>

                        <!-- Formula preview -->
                        <div class="bg-slate-950 p-4 rounded-xl border border-slate-800 font-mono text-xs space-y-2">
                            <p class="text-slate-500 font-sans font-medium text-xs">Fórmulas simuladas en tiempo real:</p>
                            <p class="text-slate-300"><span class="text-purple-400">PROMEDIO</span> = (<span id="txt-p1">8</span> + <span id="txt-p2">9</span> + <span id="txt-p3">7</span>) / 3 = <span id="txt-avg" class="text-amber-400">8.0</span></p>
                            <p class="text-slate-300"><span class="text-emerald-400">PONDERADO</span> = (<span id="txt-w1">3.2</span>) + (<span id="txt-w2">3.6</span>) + (<span id="txt-w3">1.4</span>) = <span id="txt-final" class="text-emerald-300 font-bold">8.2</span></p>
                            <div class="pt-2 border-t border-slate-800 text-slate-400">
                                =SI(<span class="text-emerald-300">8.2</span> &gt;= 6.0, <span class="text-emerald-400">"APROBADO"</span>, <span class="text-rose-400">"REPROBADO"</span>)
                            </div>
                        </div>

                        <!-- Result Display -->
                        <div class="bg-slate-800 rounded-xl p-4 flex flex-col justify-center items-center text-center border border-slate-700">
                            <span class="text-xs text-slate-400 uppercase tracking-wider font-semibold">Calificación Final</span>
                            <span id="final-score" class="text-4xl font-extrabold text-emerald-400 my-1">8.2</span>
                            <span id="status-badge" class="px-3 py-1 rounded-full text-xs font-bold bg-emerald-500/20 text-emerald-300 border border-emerald-500/30">
                                ¡APROBADO!
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- MODULE 3: POWERPOINT -->
        <section id="tab-powerpoint" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-2xl p-6 sm:p-8 border border-slate-200 shadow-sm">
                <div class="flex items-center gap-4 mb-6">
                    <div class="w-12 h-12 bg-orange-100 text-orange-600 rounded-xl flex items-center justify-center text-2xl font-bold">
                        <i class="fa-solid fa-display"></i>
                    </div>
                    <div>
                        <h1 class="text-2xl sm:text-3xl font-extrabold text-slate-900">PowerPoint y Presentaciones Eficaces</h1>
                        <p class="text-slate-600 text-sm sm:text-base">Aprende a exponer sin aburrir a tu grupo ni saturate de texto.</p>
                    </div>
                </div>

                <div class="grid md:grid-cols-3 gap-6">
                    <!-- Rule 6x6 -->
                    <div class="bg-orange-50/50 p-5 rounded-xl border border-orange-200 space-y-3">
                        <div class="w-10 h-10 bg-orange-500 text-white rounded-lg flex items-center justify-center font-bold text-lg">6x6</div>
                        <h2 class="font-bold text-slate-900">La Regla de Oro 6x6</h2>
                        <p class="text-xs text-slate-600">Un error clásico de prepa es llenar la diapositiva de párrafos e ir a leerlos. Evítalo:</p>
                        <ul class="text-xs text-slate-700 space-y-1.5 list-disc list-inside">
                            <li>Máximo <strong>6 líneas de texto</strong> por diapositiva.</li>
                            <li>Máximo <strong>6 palabras</strong> por línea.</li>
                            <li>La diapositiva apoya tu explicación, no la sustituye.</li>
                        </ul>
                    </div>

                    <!-- Typography & Contrast -->
                    <div class="bg-slate-50 p-5 rounded-xl border border-slate-200 space-y-3">
                        <div class="w-10 h-10 bg-slate-800 text-white rounded-lg flex items-center justify-center font-bold text-lg"><i class="fa-solid fa-font"></i></div>
                        <h2 class="font-bold text-slate-900">Jerarquía Visual y Contraste</h2>
                        <p class="text-xs text-slate-600">Asegúrate de que tus diapositivas se lean perfecto desde el fondo del salón:</p>
                        <ul class="text-xs text-slate-700 space-y-1.5 list-disc list-inside">
                            <li><strong>Títulos:</strong> 36pt a 44pt (Negrita).</li>
                            <li><strong>Cuerpo de texto:</strong> 20pt a 28pt.</li>
                            <li><strong>Contraste:</strong> Fondo claro con texto oscuro, o fondo muy oscuro con letra blanca.</li>
                        </ul>
                    </div>

                    <!-- Animations & Export -->
                    <div class="bg-slate-50 p-5 rounded-xl border border-slate-200 space-y-3">
                        <div class="w-10 h-10 bg-slate-800 text-white rounded-lg flex items-center justify-center font-bold text-lg"><i class="fa-solid fa-film"></i></div>
                        <h2 class="font-bold text-slate-900">Transiciones y Exportación</h2>
                        <p class="text-xs text-slate-600">El diseño moderno prioriza lo limpio sobre los efectos exagerados:</p>
                        <ul class="text-xs text-slate-700 space-y-1.5 list-disc list-inside">
                            <li>Usa únicamente transiciones sobrias como <em>"Transformar"</em> o <em>"Desvanecer"</em>.</li>
                            <li>Evita efectos con sonido estridente.</li>
                            <li>Guarda tu archivo como <strong>PDF</strong> antes de llevarlo en la USB para no perder fuentes ni formatos.</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- MODULE 4: SEGURIDAD Y WEB -->
        <section id="tab-seguridad" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-2xl p-6 sm:p-8 border border-slate-200 shadow-sm">
                <div class="flex items-center gap-4 mb-6">
                    <div class="w-12 h-12 bg-rose-100 text-rose-600 rounded-xl flex items-center justify-center text-2xl font-bold">
                        <i class="fa-solid fa-shield-halved"></i>
                    </div>
                    <div>
                        <h1 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Navegación Web Inteligente y Ciberseguridad</h1>
                        <p class="text-slate-600 text-sm sm:text-base">Busca información relevante en segundos y protégete de estafas digitales.</p>
                    </div>
                </div>

                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Google Advanced Tricks -->
                    <div class="space-y-4">
                        <h2 class="text-lg font-bold text-slate-900 flex items-center gap-2">
                            <i class="fa-solid fa-magnifying-glass text-rose-500"></i> Comandos de Búsqueda Avanzada en Google
                        </h2>
                        <div class="space-y-3">
                            <div class="p-3 bg-slate-50 rounded-lg border border-slate-200">
                                <span class="font-mono text-xs bg-rose-100 text-rose-800 font-bold px-2 py-0.5 rounded">"frase exacta"</span>
                                <p class="text-xs text-slate-600 mt-1">Busca la coincidencia literal. Ej: <code class="text-slate-800">"Revolución Mexicana causas"</code></p>
                            </div>
                            <div class="p-3 bg-slate-50 rounded-lg border border-slate-200">
                                <span class="font-mono text-xs bg-rose-100 text-rose-800 font-bold px-2 py-0.5 rounded">filetype:pdf</span>
                                <p class="text-xs text-slate-600 mt-1">Filtra solo documentos o libros descargables. Ej: <code class="text-slate-800">fisica II filetype:pdf</code></p>
                            </div>
                            <div class="p-3 bg-slate-50 rounded-lg border border-slate-200">
                                <span class="font-mono text-xs bg-rose-100 text-rose-800 font-bold px-2 py-0.5 rounded">site:.edu / site:.gob</span>
                                <p class="text-xs text-slate-600 mt-1">Filtra solo información proveniente de instituciones educativas o gubernamentales confiables.</p>
                            </div>
                        </div>
                    </div>

                    <!-- Cybersecurity & Phishing -->
                    <div class="space-y-4">
                        <h2 class="text-lg font-bold text-slate-900 flex items-center gap-2">
                            <i class="fa-solid fa-lock text-rose-500"></i> Ciberseguridad para Estudiantes
                        </h2>
                        <div class="bg-rose-50/60 p-4 rounded-xl border border-rose-100 space-y-3">
                            <div class="flex items-start gap-3">
                                <i class="fa-solid fa-fish text-rose-500 text-lg mt-0.5"></i>
                                <div>
                                    <h3 class="font-bold text-xs sm:text-sm text-slate-900">¿Qué es el Phishing?</h3>
                                    <p class="text-xs text-slate-600">Mensajes de texto o correos falsos que simulan ser de tu escuela o red social para robarte tu contraseña. Siempre verifica el remitente.</p>
                                </div>
                            </div>
                            <div class="flex items-start gap-3">
                                <i class="fa-solid fa-key text-rose-500 text-lg mt-0.5"></i>
                                <div>
                                    <h3 class="font-bold text-xs sm:text-sm text-slate-900">Contraseñas Fuertes y 2FA</h3>
                                    <p class="text-xs text-slate-600">Usa más de 12 caracteres mezclando letras, números y símbolos. Activa la verificación en dos pasos (2FA) en tu correo institucional y redes.</p>
                                </div>
                            </div>
                            <div class="flex items-start gap-3">
                                <i class="fa-solid fa-user-shield text-rose-500 text-lg mt-0.5"></i>
                                <div>
                                    <h3 class="font-bold text-xs sm:text-sm text-slate-900">Privacidad en Redes</h3>
                                    <p class="text-xs text-slate-600">Nunca compartas fotos de credenciales, horarios de clase ni direcciones en cuentas públicas.</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- MODULE 5: NUBE Y TRABAJO COLABORATIVO -->
        <section id="tab-nube" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-2xl p-6 sm:p-8 border border-slate-200 shadow-sm">
                <div class="flex items-center gap-4 mb-6">
                    <div class="w-12 h-12 bg-indigo-100 text-indigo-600 rounded-xl flex items-center justify-center text-2xl font-bold">
                        <i class="fa-solid fa-cloud"></i>
                    </div>
                    <div>
                        <h1 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Herramientas de Nube y Colaboración</h1>
                        <p class="text-slate-600 text-sm sm:text-base">Trabaja en equipo en tiempo real sin perder archivos ni enviar miles de correos.</p>
                    </div>
                </div>

                <div class="grid md:grid-cols-3 gap-6">
                    <div class="p-5 rounded-xl bg-slate-50 border border-slate-200 space-y-2">
                        <div class="text-indigo-600 font-bold text-sm flex items-center gap-2">
                            <i class="fa-solid fa-users"></i> Trabajar Simultáneamente
                        </div>
                        <p class="text-xs text-slate-600">Con Google Drive o OneDrive, varios compañeros pueden redactar el mismo documento a la vez. Verás sus cursores identificados con colores.</p>
                    </div>

                    <div class="p-5 rounded-xl bg-slate-50 border border-slate-200 space-y-2">
                        <div class="text-indigo-600 font-bold text-sm flex items-center gap-2">
                            <i class="fa-solid fa-clock-rotate-left"></i> Historial de Versiones
                        </div>
                        <p class="text-xs text-slate-600">Si alguien borró por error un párrafo importante, ve a <strong>Archivo > Historial de versiones</strong> y restaura el trabajo al estado exacto que tenía horas antes.</p>
                    </div>

                    <div class="p-5 rounded-xl bg-slate-50 border border-slate-200 space-y-2">
                        <div class="text-indigo-600 font-bold text-sm flex items-center gap-2">
                            <i class="fa-solid fa-user-lock"></i> Permisos: Lector vs Editor
                        </div>
                        <p class="text-xs text-slate-600">Al compartir un enlace, elige con cuidado: <strong>Lector</strong> (solo puede ver), <strong>Comentador</strong> (puede poner sugerencias) o <strong>Editor</strong> (puede modificar todo).</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- MODULE 6: SOPORTE TÉCNICO Y SOLUCIÓN DE PROBLEMAS -->
        <section id="tab-soporte" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-2xl p-6 sm:p-8 border border-slate-200 shadow-sm">
                <div class="flex items-center gap-4 mb-6">
                    <div class="w-12 h-12 bg-amber-100 text-amber-600 rounded-xl flex items-center justify-center text-2xl font-bold">
                        <i class="fa-solid fa-wrench"></i>
                    </div>
                    <div>
                        <h1 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Soporte Técnico y Solución de Errores</h1>
                        <p class="text-slate-600 text-sm sm:text-base">Aprende a resolver los problemas tecnológicos más molestos antes de entrar en pánico.</p>
                    </div>
                </div>

                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Office Errors -->
                    <div class="space-y-4">
                        <h2 class="text-lg font-bold text-slate-900 border-b pb-2">Errores Comunes en Office</h2>
                        <div class="space-y-3">
                            <div class="p-3 rounded-lg border border-slate-200 bg-slate-50">
                                <h3 class="font-bold text-xs text-amber-800">1. Office no activado / Modo Lectura</h3>
                                <p class="text-xs text-slate-600 mt-1">Inicia sesión con tu correo institucional (.edu o dominio escolar) para obtener la licencia completa sin costo adicional.</p>
                            </div>
                            <div class="p-3 rounded-lg border border-slate-200 bg-slate-50">
                                <h3 class="font-bold text-xs text-amber-800">2. Se cerró Word sin guardar mi trabajo</h3>
                                <p class="text-xs text-slate-600 mt-1">Abre Word, ve a <strong>Archivo > Información > Administrar documento > Recuperar documentos no guardados</strong>.</p>
                            </div>
                            <div class="p-3 rounded-lg border border-slate-200 bg-slate-50">
                                <h3 class="font-bold text-xs text-amber-800">3. El audio/video no se reproduce en mi presentación</h3>
                                <p class="text-xs text-slate-600 mt-1">Usa siempre formatos universales como MP4 o MP3. Guarda la presentación en formato .PPTX en lugar del estándar antiguo .PPT.</p>
                            </div>
                        </div>
                    </div>

                    <!-- Excel Errors -->
                    <div class="space-y-4">
                        <h2 class="text-lg font-bold text-slate-900 border-b pb-2">Traductor de Errores de Excel</h2>
                        <div class="space-y-3">
                            <div class="p-3 rounded-lg border border-slate-200 bg-slate-50">
                                <span class="font-mono text-xs font-bold text-rose-600">#¡VALOR!</span>
                                <p class="text-xs text-slate-600 mt-0.5">Estás intentando realizar una operación matemática utilizando una celda que contiene letras o texto.</p>
                            </div>
                            <div class="p-3 rounded-lg border border-slate-200 bg-slate-50">
                                <span class="font-mono text-xs font-bold text-rose-600">#REF!</span>
                                <p class="text-xs text-slate-600 mt-0.5">La celda que la fórmula intentaba calcular fue eliminada por completo de la hoja.</p>
                            </div>
                            <div class="p-3 rounded-lg border border-slate-200 bg-slate-50">
                                <span class="font-mono text-xs font-bold text-rose-600">#¿NOMBRE?</span>
                                <p class="text-xs text-slate-600 mt-0.5">Escribiste mal la fórmula (ejemplo: pusiste <code class="text-slate-800">=SUMMA</code> en lugar de <code class="text-slate-800">=SUMA</code>).</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- MODULE 7: ATAJOS DE TECLADO E IMPRIMIBLES -->
        <section id="tab-atajos" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-2xl p-6 sm:p-8 border border-slate-200 shadow-sm">
                <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4 mb-6 border-b pb-4">
                    <div class="flex items-center gap-4">
                        <div class="w-12 h-12 bg-yellow-100 text-yellow-600 rounded-xl flex items-center justify-center text-2xl font-bold">
                            <i class="fa-solid fa-keyboard"></i>
                        </div>
                        <div>
                            <h1 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Atajos e Imprimibles Indispensables</h1>
                            <p class="text-slate-600 text-sm sm:text-base">Gana velocidad de trabajo utilizando combinaciones clave de teclado.</p>
                        </div>
                    </div>
                    <button onclick="window.print()" class="bg-slate-900 hover:bg-slate-800 text-white px-4 py-2 rounded-xl text-xs sm:text-sm font-semibold transition flex items-center gap-2">
                        <i class="fa-solid fa-print"></i> Imprimir Guía
                    </button>
                </div>

                <div class="grid md:grid-cols-3 gap-6">
                    <!-- General Windows Shortcuts -->
                    <div class="p-4 rounded-xl border border-slate-200 bg-slate-50/50 space-y-3">
                        <h2 class="font-bold text-slate-900 text-sm flex items-center gap-2 border-b pb-2">
                            <i class="fa-brands fa-windows text-blue-500"></i> Windows General
                        </h2>
                        <ul class="text-xs space-y-2 text-slate-700">
                            <li class="flex justify-between items-center"><span>Copiar</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + C</kbd></li>
                            <li class="flex justify-between items-center"><span>Pegar</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + V</kbd></li>
                            <li class="flex justify-between items-center"><span>Cortar</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + X</kbd></li>
                            <li class="flex justify-between items-center"><span>Deshacer</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + Z</kbd></li>
                            <li class="flex justify-between items-center"><span>Captura de pantalla parcial</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Win + Shift + S</kbd></li>
                            <li class="flex justify-between items-center"><span>Bloquear equipo rápidamente</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Win + L</kbd></li>
                        </ul>
                    </div>

                    <!-- Word Shortcuts -->
                    <div class="p-4 rounded-xl border border-slate-200 bg-slate-50/50 space-y-3">
                        <h2 class="font-bold text-slate-900 text-sm flex items-center gap-2 border-b pb-2">
                            <i class="fa-regular fa-file-word text-blue-600"></i> Microsoft Word
                        </h2>
                        <ul class="text-xs space-y-2 text-slate-700">
                            <li class="flex justify-between items-center"><span>Guardar documento</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + G</kbd></li>
                            <li class="flex justify-between items-center"><span>Texto en Negrita</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + N</kbd></li>
                            <li class="flex justify-between items-center"><span>Texto en Cursiva</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + K</kbd></li>
                            <li class="flex justify-between items-center"><span>Texto Subrayado</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + S</kbd></li>
                            <li class="flex justify-between items-center"><span>Centrar párrafo</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + T</kbd></li>
                            <li class="flex justify-between items-center"><span>Justificar texto</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + J</kbd></li>
                        </ul>
                    </div>

                    <!-- Excel & Web Shortcuts -->
                    <div class="p-4 rounded-xl border border-slate-200 bg-slate-50/50 space-y-3">
                        <h2 class="font-bold text-slate-900 text-sm flex items-center gap-2 border-b pb-2">
                            <i class="fa-regular fa-file-excel text-emerald-600"></i> Excel y Navegador
                        </h2>
                        <ul class="text-xs space-y-2 text-slate-700">
                            <li class="flex justify-between items-center"><span>Autosuma en celda</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Alt + =</kbd></li>
                            <li class="flex justify-between items-center"><span>Buscar término</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + B</kbd></li>
                            <li class="flex justify-between items-center"><span>Nueva pestaña web</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + T</kbd></li>
                            <li class="flex justify-between items-center"><span>Reabrir pestaña cerrada</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + Shift + T</kbd></li>
                            <li class="flex justify-between items-center"><span>Seleccionar todo</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + E</kbd></li>
                            <li class="flex justify-between items-center"><span>Imprimir rápidamente</span> <kbd class="px-2 py-0.5 bg-white border border-slate-300 rounded font-mono shadow-2xs">Ctrl + P</kbd></li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- MODULE 8: RECURSOS Y HERRAMIENTAS GRATUITAS -->
        <section id="tab-recursos" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-2xl p-6 sm:p-8 border border-slate-200 shadow-sm">
                <div class="flex items-center gap-4 mb-6">
                    <div class="w-12 h-12 bg-teal-100 text-teal-600 rounded-xl flex items-center justify-center text-2xl font-bold">
                        <i class="fa-solid fa-cubes"></i>
                    </div>
                    <div>
                        <h1 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Recursos y Herramientas Gratuitas</h1>
                        <p class="text-slate-600 text-sm sm:text-base">Bancos de imágenes, plantillas de diseño y utilidades esenciales para tus entregas.</p>
                    </div>
                </div>

                <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-4">
                    <!-- Slides Templates -->
                    <div class="p-4 rounded-xl border border-slate-200 hover:border-teal-400 transition bg-slate-50/50 space-y-2">
                        <div class="text-teal-600 text-xl font-bold"><i class="fa-solid fa-file-powerpoint"></i></div>
                        <h2 class="font-bold text-slate-900 text-sm">Plantillas de Presentación</h2>
                        <p class="text-xs text-slate-600">Diseños profesionales listos para usar en PowerPoint y Google Slides.</p>
                        <ul class="text-xs font-semibold text-teal-700 space-y-1 pt-1">
                            <li>• Slidesgo</li>
                            <li>• SlidesCarnival</li>
                        </ul>
                    </div>

                    <!-- Image Banks -->
                    <div class="p-4 rounded-xl border border-slate-200 hover:border-teal-400 transition bg-slate-50/50 space-y-2">
                        <div class="text-teal-600 text-xl font-bold"><i class="fa-solid fa-image"></i></div>
                        <h2 class="font-bold text-slate-900 text-sm">Bancos de Imágenes Libres</h2>
                        <p class="text-xs text-slate-600">Fotografías en alta resolución libres de derechos de autor para tus trabajos.</p>
                        <ul class="text-xs font-semibold text-teal-700 space-y-1 pt-1">
                            <li>• Unsplash</li>
                            <li>• Pexels</li>
                            <li>• Pixabay</li>
                        </ul>
                    </div>

                    <!-- PDF Tools -->
                    <div class="p-4 rounded-xl border border-slate-200 hover:border-teal-400 transition bg-slate-50/50 space-y-2">
                        <div class="text-teal-600 text-xl font-bold"><i class="fa-solid fa-file-pdf"></i></div>
                        <h2 class="font-bold text-slate-900 text-sm">Herramientas PDF</h2>
                        <p class="text-xs text-slate-600">Une, divide, comprime o convierte archivos PDF en segundos directamente en línea.</p>
                        <ul class="text-xs font-semibold text-teal-700 space-y-1 pt-1">
                            <li>• ILovePDF</li>
                            <li>• Smallpdf</li>
                        </ul>
                    </div>

                    <!-- Fonts & Icons -->
                    <div class="p-4 rounded-xl border border-slate-200 hover:border-teal-400 transition bg-slate-50/50 space-y-2">
                        <div class="text-teal-600 text-xl font-bold"><i class="fa-solid fa-font"></i></div>
                        <h2 class="font-bold text-slate-900 text-sm">Fuentes e Iconos</h2>
                        <p class="text-xs text-slate-600">Tipografías gratuitas para descargar e iconos vectoriales para personalizar.</p>
                        <ul class="text-xs font-semibold text-teal-700 space-y-1 pt-1">
                            <li>• Google Fonts</li>
                            <li>• FontAwesome</li>
                            <li>• Flaticon</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- MODULE 9: PREGUNTAS FRECUENTES (FAQ) -->
        <section id="tab-faq" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-2xl p-6 sm:p-8 border border-slate-200 shadow-sm">
                <div class="flex items-center gap-4 mb-6">
                    <div class="w-12 h-12 bg-purple-100 text-purple-600 rounded-xl flex items-center justify-center text-2xl font-bold">
                        <i class="fa-solid fa-circle-question"></i>
                    </div>
                    <div>
                        <h1 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Preguntas Frecuentes (FAQ)</h1>
                        <p class="text-slate-600 text-sm sm:text-base">Respuestas rápidas a las dudas comunes en entornos escolares virtuales.</p>
                    </div>
                </div>

                <div class="space-y-4">
                    <div class="p-4 rounded-xl border border-slate-200 bg-slate-50">
                        <h2 class="font-bold text-sm text-slate-900 flex items-center gap-2">
                            <i class="fa-solid fa-graduation-cap text-purple-600"></i> ¿Cómo consigo la licencia gratuita de Microsoft Office con mi correo de la prepa?
                        </h2>
                        <p class="text-xs text-slate-600 mt-2 leading-relaxed">
                            Ingresa al portal oficial de Microsoft Office para educación (office.com/getoffice365) e ingresa tu correo institucional de estudiante (usualmente termina en <code class="text-purple-700">.edu.mx</code> o con la clave de tu institución). El sistema validará tu cuenta activa y podrás instalar el paquete completo o utilizarlo en línea totalmente gratis.
                        </p>
                    </div>

                    <div class="p-4 rounded-xl border border-slate-200 bg-slate-50">
                        <h2 class="font-bold text-sm text-slate-900 flex items-center gap-2">
                            <i class="fa-solid fa-code-compare text-purple-600"></i> ¿Cuál es la diferencia real entre Microsoft Office 365, Google Docs y LibreOffice?
                        </h2>
                        <p class="text-xs text-slate-600 mt-2 leading-relaxed">
                            <strong>Office 365</strong> es la suite más potente y estándar del mercado. <strong>Google Docs</strong> funciona directamente en la nube y es la mejor para colaborar en tiempo real de forma ágil. <strong>LibreOffice</strong> es un software 100% gratuito e instalable de código abierto que no requiere internet.
                        </p>
                    </div>

                    <div class="p-4 rounded-xl border border-slate-200 bg-slate-50">
                        <h2 class="font-bold text-sm text-slate-900 flex items-center gap-2">
                            <i class="fa-solid fa-upload text-purple-600"></i> ¿Cómo entregar tareas correctamente en Classroom, Teams o Canvas sin que falle el archivo?
                        </h2>
                        <p class="text-xs text-slate-600 mt-2 leading-relaxed">
                            Asegúrate de convertir tu trabajo a formato <strong>PDF</strong> a menos que el profesor te pida explícitamente la hoja de cálculo o presentación editable. Revisa siempre dar clic en el botón <strong>"Entregar"</strong> o <strong>"Enviar tarea"</strong> tras adjuntar tu archivo, asegurándote de ver la confirmación en pantalla.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- MODULE 10: QUIZ DE EVALUACIÓN AMPLIADO -->
        <section id="tab-quiz" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-2xl p-6 sm:p-8 border border-slate-200 shadow-sm">
                <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4 mb-6 border-b pb-4">
                    <div class="flex items-center gap-4">
                        <div class="w-12 h-12 bg-amber-100 text-amber-600 rounded-xl flex items-center justify-center text-2xl font-bold">
                            <i class="fa-solid fa-graduation-cap"></i>
                        </div>
                        <div>
                            <h1 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Quiz de Evaluación Ampliado</h1>
                            <p class="text-slate-600 text-sm sm:text-base">Demuestra lo que has aprendido respondiendo las preguntas de todos los módulos.</p>
                        </div>
                    </div>
                    <div id="quiz-score-badge" class="bg-slate-100 border border-slate-300 text-slate-700 px-4 py-2 rounded-xl text-sm font-bold">
                        Puntaje: <span id="current-score">0</span> / 6
                    </div>
                </div>

                <form id="quiz-form" class="space-y-6">
                    <!-- Q1 -->
                    <div class="p-4 sm:p-5 rounded-xl border border-slate-200 bg-slate-50/50 space-y-3">
                        <p class="font-semibold text-sm text-slate-900">1. Según las normas APA 7.ª edición, ¿cuál es el margen estándar requerido?</p>
                        <div class="space-y-2 text-xs sm:text-sm">
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q1" value="a"> 3.0 cm superior e inferior</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q1" value="b"> 2.54 cm (1 pulgada) por todos los lados</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q1" value="c"> 1.5 cm con texto totalmente justificado</label>
                        </div>
                    </div>

                    <!-- Q2 -->
                    <div class="p-4 sm:p-5 rounded-xl border border-slate-200 bg-slate-50/50 space-y-3">
                        <p class="font-semibold text-sm text-slate-900">2. ¿Qué fórmula de Excel debes usar si quieres contar celdas solo si cumplen una regla concreta?</p>
                        <div class="space-y-2 text-xs sm:text-sm">
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q2" value="a"> =CONTAR.SI()</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q2" value="b"> =SUMAR.SI()</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q2" value="c"> =BUSCARV()</label>
                        </div>
                    </div>

                    <!-- Q3 -->
                    <div class="p-4 sm:p-5 rounded-xl border border-slate-200 bg-slate-50/50 space-y-3">
                        <p class="font-semibold text-sm text-slate-900">3. ¿En qué consiste la regla visual 6x6 para presentaciones eficientes?</p>
                        <div class="space-y-2 text-xs sm:text-sm">
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q3" value="a"> Usar 6 imágenes y 6 colores llamativos por diapositiva</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q3" value="b"> Máximo 6 líneas por diapositiva y máximo 6 palabras por línea</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q3" value="c"> Presentar exactamente 6 diapositivas en un tiempo de 6 minutos</label>
                        </div>
                    </div>

                    <!-- Q4 -->
                    <div class="p-4 sm:p-5 rounded-xl border border-slate-200 bg-slate-50/50 space-y-3">
                        <p class="font-semibold text-sm text-slate-900">4. Si deseas buscar en Google únicamente documentos en PDF sobre la tabla periódica, ¿qué filtro utilizas?</p>
                        <div class="space-y-2 text-xs sm:text-sm">
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q4" value="a"> tabla periodica filetype:pdf</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q4" value="b"> tabla periodica site:pdf</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q4" value="c"> "tabla periodica" pdf</label>
                        </div>
                    </div>

                    <!-- Q5 -->
                    <div class="p-4 sm:p-5 rounded-xl border border-slate-200 bg-slate-50/50 space-y-3">
                        <p class="font-semibold text-sm text-slate-900">5. ¿Qué significa el error #¿NOMBRE? en una celda de Microsoft Excel?</p>
                        <div class="space-y-2 text-xs sm:text-sm">
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q5" value="a"> Hay una celda borrada que era requerida por la fórmula</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q5" value="b"> Hubo un error tipográfico al escribir el nombre de la fórmula</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q5" value="c"> Se introdujo un número negativo no permitido</label>
                        </div>
                    </div>

                    <!-- Q6 -->
                    <div class="p-4 sm:p-5 rounded-xl border border-slate-200 bg-slate-50/50 space-y-3">
                        <p class="font-semibold text-sm text-slate-900">6. ¿Qué función de la nube te ayuda a recuperar un párrafo eliminado por error horas atrás?</p>
                        <div class="space-y-2 text-xs sm:text-sm">
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q6" value="a"> Modo Lector</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q6" value="b"> Historial de Versiones</label>
                            <label class="flex items-center gap-2 p-2 rounded bg-white border border-slate-200 cursor-pointer hover:bg-slate-100"><input type="radio" name="q6" value="c"> Permiso de Editor</label>
                        </div>
                    </div>

                    <div class="flex flex-col sm:flex-row gap-3 pt-2">
                        <button type="button" onclick="evaluateQuiz()" class="bg-amber-500 hover:bg-amber-600 text-slate-900 font-bold px-6 py-3 rounded-xl transition shadow">
                            <i class="fa-solid fa-paper-plane"></i> Evaluar Mis Respuestas
                        </button>
                        <button type="button" onclick="resetQuiz()" class="bg-slate-200 hover:bg-slate-300 text-slate-700 font-semibold px-4 py-3 rounded-xl transition">
                            Reiniciar Quiz
                        </button>
                    </div>
                </form>

                <!-- Feedback Box -->
                <div id="quiz-results" class="hidden p-5 rounded-xl border text-sm space-y-2">
                    <h3 id="quiz-results-title" class="font-bold text-base"></h3>
                    <p id="quiz-results-msg" class="text-xs sm:text-sm"></p>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-slate-900 text-slate-400 text-xs py-6 border-t border-slate-800 mt-8">
        <div class="max-w-7xl mx-auto px-4 text-center space-y-2">
            <p>© CompuPrepa - Guía Práctica de Computación Básica para Bachillerato.</p>
            <p class="text-slate-500">Diseñado para ser accesible, rápido e interactivo en todos tus dispositivos.</p>
        </div>
    </footer>

    <!-- Interactive JavaScript Logic -->
    <script>
        // Tab switching function
        function switchTab(tabId) {
            // Hide all tab content
            const contents = document.querySelectorAll('.tab-content');
            contents.forEach(el => el.classList.add('hidden'));

            // Deactivate all buttons
            const buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(btn => btn.classList.remove('active'));

            // Show current tab content
            const targetContent = document.getElementById('tab-' + tabId);
            if (targetContent) {
                targetContent.classList.remove('hidden');
            }

            // Activate current button
            const targetBtn = document.getElementById('btn-' + tabId);
            if (targetBtn) {
                targetBtn.classList.add('active');
            }

            // Scroll smoothly to top of main area
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Excel Grade Simulator Logic
        function calcGrades() {
            const p1 = parseFloat(document.getElementById('sim-p1').value);
            const p2 = parseFloat(document.getElementById('sim-p2').value);
            const p3 = parseFloat(document.getElementById('sim-p3').value);

            document.getElementById('val-p1').innerText = p1.toFixed(1);
            document.getElementById('val-p2').innerText = p2.toFixed(1);
            document.getElementById('val-p3').innerText = p3.toFixed(1);

            document.getElementById('txt-p1').innerText = p1;
            document.getElementById('txt-p2').innerText = p2;
            document.getElementById('txt-p3').innerText = p3;

            const avg = (p1 + p2 + p3) / 3;
            document.getElementById('txt-avg').innerText = avg.toFixed(1);

            const w1 = p1 * 0.4;
            const w2 = p2 * 0.4;
            const w3 = p3 * 0.2;

            document.getElementById('txt-w1').innerText = w1.toFixed(1);
            document.getElementById('txt-w2').innerText = w2.toFixed(1);
            document.getElementById('txt-w3').innerText = w3.toFixed(1);

            const finalScore = w1 + w2 + w3;
            const scoreFormatted = finalScore.toFixed(1);

            document.getElementById('txt-final').innerText = scoreFormatted;
            const scoreEl = document.getElementById('final-score');
            scoreEl.innerText = scoreFormatted;

            const badge = document.getElementById('status-badge');

            if (finalScore >= 6.0) {
                badge.innerText = "¡APROBADO!";
                badge.className = "px-3 py-1 rounded-full text-xs font-bold bg-emerald-500/20 text-emerald-300 border border-emerald-500/30";
                scoreEl.className = "text-4xl font-extrabold text-emerald-400 my-1";
            } else {
                badge.innerText = "REPROBADO (EXTRAORDINARIO)";
                badge.className = "px-3 py-1 rounded-full text-xs font-bold bg-rose-500/20 text-rose-300 border border-rose-500/30";
                scoreEl.className = "text-4xl font-extrabold text-rose-400 my-1";
            }
        }

        function resetGradeSim() {
            document.getElementById('sim-p1').value = 8;
            document.getElementById('sim-p2').value = 9;
            document.getElementById('sim-p3').value = 7;
            calcGrades();
        }

        // Quiz Evaluation Logic
        const correctAnswers = {
            q1: 'b',
            q2: 'a',
            q3: 'b',
            q4: 'a',
            q5: 'b',
            q6: 'b'
        };

        function evaluateQuiz() {
            const form = document.getElementById('quiz-form');
            let score = 0;
            let total = Object.keys(correctAnswers).length;

            for (let q in correctAnswers) {
                const selected = form.querySelector(`input[name="${q}"]:checked`);
                if (selected && selected.value === correctAnswers[q]) {
                    score++;
                }
            }

            document.getElementById('current-score').innerText = score;
            const resultsBox = document.getElementById('quiz-results');
            const title = document.getElementById('quiz-results-title');
            const msg = document.getElementById('quiz-results-msg');

            resultsBox.classList.remove('hidden');

            if (score === total) {
                resultsBox.className = "p-5 rounded-xl border bg-emerald-50 border-emerald-200 text-emerald-900 space-y-1 block";
                title.innerText = "¡Puntaje Perfecto! (6/6)";
                msg.innerText = "¡Felicidades! Tienes dominados los conceptos fundamentales de computación para preparatoria.";
            } else if (score >= 4) {
                resultsBox.className = "p-5 rounded-xl border bg-amber-50 border-amber-200 text-amber-900 space-y-1 block";
                title.innerText = `Buen Resultado: ${score} de ${total}`;
                msg.innerText = "Demuestras buen conocimiento general, pero vale la pena repasar los módulos donde fallaste.";
            } else {
                resultsBox.className = "p-5 rounded-xl border bg-rose-50 border-rose-200 text-rose-900 space-y-1 block";
                title.innerText = `Necesitas Repasar: ${score} de ${total}`;
                msg.innerText = "Te recomendamos revisar con atención los módulos de Word, Excel y Seguridad antes de volver a intentarlo.";
            }
        }

        function resetQuiz() {
            document.getElementById('quiz-form').reset();
            document.getElementById('current-score').innerText = "0";
            document.getElementById('quiz-results').classList.add('hidden');
        }

        // Initialize defaults
        window.onload = function() {
            calcGrades();
        };
    </script>
</body>
</html>
