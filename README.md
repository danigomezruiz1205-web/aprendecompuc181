[Uploading aprende_computaci_n_b_sica (2).html…]()
<!DOCTYPE html>
<html lang="es-MX" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Computación Básica | Guía de Informática para Prepa</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        mono: ['JetBrains Mono', 'monospace'],
                    },
                    colors: {
                        navy: {
                            800: '#1e293b',
                            900: '#0f172a',
                            950: '#020617',
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
            box-shadow: 0 2px 4px rgba(2, 132, 199, 0.25);
        }
    </style>
</head>
<body class="bg-slate-100 text-slate-800 font-sans antialiased min-h-screen flex flex-col">

    <!-- Header & Navigation -->
    <header class="bg-navy-900 text-white sticky top-0 z-50 shadow-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center gap-3 cursor-pointer" onclick="switchTab('word')">
                    <div class="bg-sky-600 text-white p-2 rounded-lg font-bold">
                        <i class="fa-solid fa-terminal text-lg"></i>
                    </div>
                    <div>
                        <span class="font-extrabold text-lg sm:text-xl tracking-tight text-white block leading-none">Informática Prepa</span>
                        <span class="text-xs text-sky-400 font-medium">Manual práctico de herramientas digitales</span>
                    </div>
                </div>
                <div class="hidden sm:flex items-center gap-3">
                    <button onclick="switchTab('quiz')" class="bg-sky-600 hover:bg-sky-500 text-white font-semibold text-xs px-3 py-2 rounded-lg transition">
                        <i class="fa-solid fa-clipboard-check mr-1"></i> Examen (10 Preguntas)
                    </button>
                    <button onclick="switchTab('soporte')" class="bg-slate-800 hover:bg-slate-700 text-slate-200 border border-slate-700 text-xs px-3 py-2 rounded-lg transition">
                        <i class="fa-solid fa-wrench mr-1 text-amber-400"></i> Ayuda Rápida
                    </button>
                </div>
            </div>
        </div>

        <!-- Scrollable Tabs Nav -->
        <nav class="bg-navy-950 border-t border-slate-800 px-2 sm:px-4">
            <div class="max-w-7xl mx-auto flex space-x-1 overflow-x-auto py-2 no-scrollbar text-xs font-semibold">
                <button onclick="switchTab('word')" id="btn-word" class="tab-btn active shrink-0 px-3 py-2 rounded-md text-slate-300 hover:text-white hover:bg-slate-800 transition flex items-center gap-1.5">
                    <i class="fa-solid fa-file-word text-blue-400"></i> Word
                </button>
                <button onclick="switchTab('excel')" id="btn-excel" class="tab-btn shrink-0 px-3 py-2 rounded-md text-slate-300 hover:text-white hover:bg-slate-800 transition flex items-center gap-1.5">
                    <i class="fa-solid fa-file-excel text-emerald-400"></i> Excel
                </button>
                <button onclick="switchTab('powerpoint')" id="btn-powerpoint" class="tab-btn shrink-0 px-3 py-2 rounded-md text-slate-300 hover:text-white hover:bg-slate-800 transition flex items-center gap-1.5">
                    <i class="fa-solid fa-file-powerpoint text-orange-400"></i> PowerPoint
                </button>
                <button onclick="switchTab('nube')" id="btn-nube" class="tab-btn shrink-0 px-3 py-2 rounded-md text-slate-300 hover:text-white hover:bg-slate-800 transition flex items-center gap-1.5">
                    <i class="fa-solid fa-cloud text-indigo-400"></i> Nube y Colaboración
                </button>
                <button onclick="switchTab('seguridad')" id="btn-seguridad" class="tab-btn shrink-0 px-3 py-2 rounded-md text-slate-300 hover:text-white hover:bg-slate-800 transition flex items-center gap-1.5">
                    <i class="fa-solid fa-shield-halved text-rose-400"></i> Seguridad y Búsquedas
                </button>
                <button onclick="switchTab('soporte')" id="btn-soporte" class="tab-btn shrink-0 px-3 py-2 rounded-md text-slate-300 hover:text-white hover:bg-slate-800 transition flex items-center gap-1.5">
                    <i class="fa-solid fa-wrench text-amber-400"></i> Soporte Técnico
                </button>
                <button onclick="switchTab('atajos')" id="btn-atajos" class="tab-btn shrink-0 px-3 py-2 rounded-md text-slate-300 hover:text-white hover:bg-slate-800 transition flex items-center gap-1.5">
                    <i class="fa-solid fa-keyboard text-yellow-400"></i> Atajos
                </button>
                <button onclick="switchTab('recursos')" id="btn-recursos" class="tab-btn shrink-0 px-3 py-2 rounded-md text-slate-300 hover:text-white hover:bg-slate-800 transition flex items-center gap-1.5">
                    <i class="fa-solid fa-folder-open text-teal-400"></i> Recursos
                </button>
                <button onclick="switchTab('faq')" id="btn-faq" class="tab-btn shrink-0 px-3 py-2 rounded-md text-slate-300 hover:text-white hover:bg-slate-800 transition flex items-center gap-1.5">
                    <i class="fa-solid fa-circle-question text-purple-400"></i> FAQ
                </button>
                <button onclick="switchTab('quiz')" id="btn-quiz" class="tab-btn shrink-0 px-3 py-2 rounded-md text-slate-300 hover:text-white hover:bg-slate-800 transition flex items-center gap-1.5">
                    <i class="fa-solid fa-graduation-cap text-sky-400"></i> Examen
                </button>
            </div>
        </nav>
    </header>

    <!-- Main Content Body -->
    <main class="flex-grow max-w-7xl w-full mx-auto p-4 sm:p-6 lg:p-8">

        <!-- 1. WORD -->
        <section id="tab-word" class="tab-content space-y-6">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm">
                <div class="border-b border-slate-200 pb-4 mb-6">
                    <h1 class="text-2xl font-bold text-slate-900">Procesador de Textos: Microsoft Word</h1>
                    <p class="text-sm text-slate-600 mt-1">Configuración técnica de documentos académicos y formato APA para entregas escolares.</p>
                </div>

                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Formato APA -->
                    <div class="bg-slate-50 p-5 rounded-lg border border-slate-200 space-y-3">
                        <h2 class="font-bold text-slate-900 text-sm flex items-center gap-2">
                            <i class="fa-solid fa-align-left text-blue-600"></i> Parámetros Estándar APA (7.ª edición)
                        </h2>
                        <ul class="text-xs text-slate-700 space-y-2">
                            <li class="bg-white p-2 rounded border border-slate-200"><strong>Márgenes:</strong> 2.54 cm (1 pulgada) en los 4 costados. Configúralo en <i>Disposición > Márgenes > Normal</i>.</li>
                            <li class="bg-white p-2 rounded border border-slate-200"><strong>Fuente:</strong> Arial 11 pt, Calibri 11 pt o Times New Roman 12 pt. Mantén una sola en todo el trabajo.</li>
                            <li class="bg-white p-2 rounded border border-slate-200"><strong>Interlineado:</strong> 2.0 (Doble) sin espacio adicional entre párrafos.</li>
                            <li class="bg-white p-2 rounded border border-slate-200"><strong>Sangría:</strong> 1.27 cm en la primera línea de cada párrafo (presiona la tecla <kbd class="font-mono bg-slate-100 px-1 border rounded">Tab</kbd>).</li>
                        </ul>
                    </div>

                    <!-- Estructura y Tablas de Contenido -->
                    <div class="bg-slate-50 p-5 rounded-lg border border-slate-200 space-y-3">
                        <h2 class="font-bold text-slate-900 text-sm flex items-center gap-2">
                            <i class="fa-solid fa-list-check text-blue-600"></i> Índices Automáticos y Saltos
                        </h2>
                        <div class="space-y-2 text-xs text-slate-700">
                            <p class="font-semibold text-slate-800">1. Aplica Estilos de Título:</p>
                            <p class="bg-white p-2 rounded border border-slate-200">Selecciona los encabezados principales y asigna <span class="font-mono font-bold text-blue-700">Título 1</span> desde la pestaña <i>Inicio</i>. Para subtítulos, usa <span class="font-mono font-bold text-blue-700">Título 2</span>.</p>
                            
                            <p class="font-semibold text-slate-800 mt-2">2. Genera el Índice:</p>
                            <p class="bg-white p-2 rounded border border-slate-200">Ubícate en la página correspondiente y selecciona <i>Referencias > Tabla de contenido > Tabla automática</i>.</p>

                            <p class="font-semibold text-slate-800 mt-2">3. Saltos de Sección:</p>
                            <p class="bg-white p-2 rounded border border-slate-200">Si necesitas colocar una tabla horizontal o cambiar el número de página a partir de la introducción, inserta un salto desde <i>Disposición > Saltos > Página siguiente</i>.</p>
                        </div>
                    </div>
                </div>

                <!-- Encabezados y Pies de página -->
                <div class="mt-6 bg-blue-50/50 p-4 rounded-lg border border-blue-100 text-xs text-slate-700">
                    <span class="font-bold text-blue-900 block mb-1">Numeración de páginas sin afectar la portada:</span>
                    Para omitir el número en la primera hoja, haz doble clic sobre el encabezado/pie de página y activa la casilla <span class="font-semibold">"Primera página diferente"</span> en la barra superior.
                </div>
            </div>
        </section>

        <!-- 2. EXCEL -->
        <section id="tab-excel" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm">
                <div class="border-b border-slate-200 pb-4 mb-6">
                    <h1 class="text-2xl font-bold text-slate-900">Hoja de Cálculo: Microsoft Excel</h1>
                    <p class="text-sm text-slate-600 mt-1">Estructura de datos, sintaxis de fórmulas y procesamiento aritmético básico.</p>
                </div>

                <!-- Fórmulas indispensables -->
                <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4 mb-6">
                    <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200">
                        <span class="font-mono text-xs font-bold text-emerald-800 bg-emerald-100 px-2 py-0.5 rounded block w-fit mb-1.5">=SUMA(A1:A10)</span>
                        <p class="text-xs text-slate-600">Calcula el total sumando los valores numéricos del rango seleccionado.</p>
                    </div>
                    <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200">
                        <span class="font-mono text-xs font-bold text-emerald-800 bg-emerald-100 px-2 py-0.5 rounded block w-fit mb-1.5">=PROMEDIO(B1:B5)</span>
                        <p class="text-xs text-slate-600">Obtiene la media aritmética exacta de un grupo de celdas numéricas.</p>
                    </div>
                    <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200">
                        <span class="font-mono text-xs font-bold text-emerald-800 bg-emerald-100 px-2 py-0.5 rounded block w-fit mb-1.5">=SI(A1>=6, "Aprobado", "Reprobado")</span>
                        <p class="text-xs text-slate-600">Devuelve un texto o resultado específico según el cumplimiento de una condición.</p>
                    </div>
                    <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200">
                        <span class="font-mono text-xs font-bold text-emerald-800 bg-emerald-100 px-2 py-0.5 rounded block w-fit mb-1.5">=CONTAR.SI(C1:C20, ">=6")</span>
                        <p class="text-xs text-slate-600">Cuenta cuántas celdas dentro de un rango cumplen un criterio dado.</p>
                    </div>
                    <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200">
                        <span class="font-mono text-xs font-bold text-emerald-800 bg-emerald-100 px-2 py-0.5 rounded block w-fit mb-1.5">=BUSCARV(D2, A1:B50, 2, FALSO)</span>
                        <p class="text-xs text-slate-600">Busca un dato en la primera columna de una tabla y extrae el valor de la columna vecina.</p>
                    </div>
                    <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200">
                        <span class="font-semibold text-xs text-slate-800 block mb-1">Formato Condicional & Gráficas</span>
                        <p class="text-xs text-slate-600">Resalta celdas automáticamente (ej. reprobados en rojo) y representa datos con gráficos de barras o pastel.</p>
                    </div>
                </div>

                <!-- SIMULADOR INTERACTIVO DE EXCEL -->
                <div class="bg-navy-900 text-white rounded-xl p-5 shadow-inner space-y-4">
                    <div class="border-b border-slate-800 pb-3 flex flex-col sm:flex-row justify-between items-start sm:items-center gap-2">
                        <div>
                            <h2 class="font-bold text-emerald-400 text-base flex items-center gap-2">
                                <i class="fa-solid fa-calculator"></i> Simulador de Fórmulas: Cálculo de Calificación Final
                            </h2>
                            <p class="text-xs text-slate-400">Ingresa las notas de tus parciales y el porcentaje del examen final para calcular el promedio final en tiempo real.</p>
                        </div>
                        <button onclick="resetSim()" class="text-xs bg-slate-800 hover:bg-slate-700 text-slate-300 px-3 py-1.5 rounded transition">
                            <i class="fa-solid fa-rotate-left mr-1"></i> Restablecer
                        </button>
                    </div>

                    <div class="grid lg:grid-cols-3 gap-6 text-slate-800">
                        <!-- Entrada de datos -->
                        <div class="bg-white p-4 rounded-lg space-y-3">
                            <h3 class="text-xs font-bold uppercase text-slate-500 tracking-wider">Notas Parciales (0 - 10)</h3>
                            <div class="grid grid-cols-2 gap-2 text-xs">
                                <div>
                                    <label class="block font-medium mb-1">Matemáticas</label>
                                    <input type="number" id="sim-m1" min="0" max="10" step="0.5" value="8" oninput="runExcelSim()" class="w-full p-2 border border-slate-300 rounded font-mono">
                                </div>
                                <div>
                                    <label class="block font-medium mb-1">Química</label>
                                    <input type="number" id="sim-m2" min="0" max="10" step="0.5" value="7.5" oninput="runExcelSim()" class="w-full p-2 border border-slate-300 rounded font-mono">
                                </div>
                                <div>
                                    <label class="block font-medium mb-1">Historia</label>
                                    <input type="number" id="sim-m3" min="0" max="10" step="0.5" value="9" oninput="runExcelSim()" class="w-full p-2 border border-slate-300 rounded font-mono">
                                </div>
                                <div>
                                    <label class="block font-medium mb-1">Español</label>
                                    <input type="number" id="sim-m4" min="0" max="10" step="0.5" value="6" oninput="runExcelSim()" class="w-full p-2 border border-slate-300 rounded font-mono">
                                </div>
                            </div>
                            <div class="pt-2 border-t border-slate-200">
                                <label class="block text-xs font-medium mb-1">Peso Examen Final: <span id="lbl-weight" class="font-mono font-bold text-blue-600">40%</span></label>
                                <input type="range" id="sim-weight" min="10" max="60" step="5" value="40" oninput="runExcelSim()" class="w-full accent-emerald-500">
                                <div class="mt-1">
                                    <label class="block text-xs font-medium mb-1">Calificación Examen Final</label>
                                    <input type="number" id="sim-exam" min="0" max="10" step="0.5" value="8.5" oninput="runExcelSim()" class="w-full p-2 border border-slate-300 rounded font-mono text-xs">
                                </div>
                            </div>
                        </div>

                        <!-- Sintaxis simulada -->
                        <div class="bg-navy-950 p-4 rounded-lg font-mono text-xs text-slate-300 space-y-2 border border-slate-800 flex flex-col justify-between">
                            <div>
                                <span class="text-slate-500 font-sans text-xs block mb-2 font-semibold">Cálculo de fórmulas en celdas:</span>
                                <p class="text-slate-400">Promedio Parciales (<span class="text-emerald-400">PROMEDIO</span>):</p>
                                <p class="text-white bg-slate-900 p-1.5 rounded border border-slate-800">=PROMEDIO(A2:D2) &rarr; <span id="out-avg-parcial" class="text-amber-400 font-bold">7.63</span></p>
                            </div>
                            <div>
                                <p class="text-slate-400">Ponderación Final (<span class="text-emerald-400">Fórmula combinada</span>):</p>
                                <p class="text-white bg-slate-900 p-1.5 rounded border border-slate-800">(<span id="out-p-weight">7.63</span> * <span id="out-w1">0.6</span>) + (<span id="out-e-val">8.5</span> * <span id="out-w2">0.4</span>)</p>
                            </div>
                            <div>
                                <p class="text-slate-400">Resultado Lógico (<span class="text-emerald-400">SI</span>):</p>
                                <p class="text-white bg-slate-900 p-1.5 rounded border border-slate-800">=SI(<span id="out-final-val">7.98</span> &gt;= 6, "APROBADO", "EXTRAORDINARIO")</p>
                            </div>
                        </div>

                        <!-- Cuadro de resultado final -->
                        <div class="bg-slate-800 p-5 rounded-lg border border-slate-700 flex flex-col items-center justify-center text-center space-y-2">
                            <span class="text-xs text-slate-400 font-semibold uppercase tracking-wider">Promedio Final Calculado</span>
                            <span id="out-score" class="text-5xl font-extrabold text-emerald-400 font-mono">7.98</span>
                            <span id="out-badge" class="px-3 py-1 rounded-full text-xs font-bold bg-emerald-500/20 text-emerald-300 border border-emerald-500/30">
                                Estatus: APROBADO
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 3. POWERPOINT -->
        <section id="tab-powerpoint" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm">
                <div class="border-b border-slate-200 pb-4 mb-6">
                    <h1 class="text-2xl font-bold text-slate-900">Presentaciones: Microsoft PowerPoint</h1>
                    <p class="text-sm text-slate-600 mt-1">Reglas de estructuración visual, manejo de archivos multimedia y exportación.</p>
                </div>

                <div class="grid md:grid-cols-3 gap-6">
                    <!-- Regla 6x6 -->
                    <div class="bg-orange-50/60 p-5 rounded-lg border border-orange-200 space-y-2">
                        <span class="bg-orange-600 text-white font-mono font-bold text-xs px-2 py-0.5 rounded inline-block mb-1">Regla 6 x 6</span>
                        <h2 class="font-bold text-slate-900 text-sm">Límite de Contenido</h2>
                        <p class="text-xs text-slate-600">Para evitar diapositivas saturadas de texto que dificultan la lectura:</p>
                        <ul class="text-xs text-slate-700 space-y-1.5 list-disc list-inside mt-2">
                            <li>Máximo <strong>6 líneas de texto</strong> por diapositiva.</li>
                            <li>Máximo <strong>6 palabras</strong> por cada línea.</li>
                            <li>Usa viñetas para anotar solo conceptos clave.</li>
                        </ul>
                    </div>

                    <!-- Multimedia sin trabas -->
                    <div class="bg-slate-50 p-5 rounded-lg border border-slate-200 space-y-2">
                        <span class="bg-slate-800 text-white font-mono font-bold text-xs px-2 py-0.5 rounded inline-block mb-1">Multimedia</span>
                        <h2 class="font-bold text-slate-900 text-sm">Insertar Audio y Video</h2>
                        <p class="text-xs text-slate-600">Evita que los videos no se reproduzcan en la computadora del salón:</p>
                        <ul class="text-xs text-slate-700 space-y-1.5 list-disc list-inside mt-2">
                            <li>Descarga videos siempre en formato <strong>MP4</strong> y audios en <strong>MP3</strong>.</li>
                            <li>Guarda la presentación y los archivos de video dentro de la misma carpeta.</li>
                            <li>Asegúrate de guardar el archivo con la extensión moderna <code class="font-mono text-slate-900 bg-slate-200 px-1 rounded">.pptx</code>.</li>
                        </ul>
                    </div>

                    <!-- Exportación -->
                    <div class="bg-slate-50 p-5 rounded-lg border border-slate-200 space-y-2">
                        <span class="bg-slate-800 text-white font-mono font-bold text-xs px-2 py-0.5 rounded inline-block mb-1">Formatos</span>
                        <h2 class="font-bold text-slate-900 text-sm">Exportar a PDF o Video</h2>
                        <p class="text-xs text-slate-600">Si solo vas a exponer sin animaciones complejas:</p>
                        <ul class="text-xs text-slate-700 space-y-1.5 list-disc list-inside mt-2">
                            <li>Exporta la presentación a <strong>PDF</strong> via <i>Archivo > Guardar como > PDF</i>. Evita desajustes de tipografía.</li>
                            <li>Si requiere reproducción automática, usa <i>Exportar > Crear un video (.MP4)</i>.</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- 4. NUBE Y COLABORACIÓN -->
        <section id="tab-nube" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm">
                <div class="border-b border-slate-200 pb-4 mb-6">
                    <h1 class="text-2xl font-bold text-slate-900">Nube y Trabajo Colaborativo</h1>
                    <p class="text-sm text-slate-600 mt-1">Uso de Google Workspace, Microsoft 365, permisos de archivo y control de cambios.</p>
                </div>

                <div class="grid md:grid-cols-3 gap-6">
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2">
                        <h2 class="font-bold text-sm text-slate-900 flex items-center gap-2">
                            <i class="fa-solid fa-user-lock text-indigo-600"></i> Control de Permisos
                        </h2>
                        <p class="text-xs text-slate-600">Al compartir enlaces en Drive o OneDrive, distingue correctamente los accesos:</p>
                        <ul class="text-xs text-slate-700 space-y-1 border-t border-slate-200 pt-2 mt-2">
                            <li><strong>Lector:</strong> Solo permite visualizar y descargar.</li>
                            <li><strong>Comentador:</strong> Permite dejar notas al margen sin modificar el texto.</li>
                            <li><strong>Editor:</strong> Otorga control total para cambiar, agregar o borrar contenido.</li>
                        </ul>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2">
                        <h2 class="font-bold text-sm text-slate-900 flex items-center gap-2">
                            <i class="fa-solid fa-rotate-left text-indigo-600"></i> Historial de Versiones
                        </h2>
                        <p class="text-xs text-slate-600">Si un compañero borró por error una sección completa del trabajo en equipo:</p>
                        <p class="text-xs text-slate-700 bg-white p-2 rounded border border-slate-200 mt-2">
                            Abre el archivo y selecciona <i>Archivo > Historial de versiones</i>. Permite revisar los cambios realizados por cada integrante y restaurar cualquier punto anterior.
                        </p>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2">
                        <h2 class="font-bold text-sm text-slate-900 flex items-center gap-2">
                            <i class="fa-solid fa-folder-tree text-indigo-600"></i> Sincronización
                        </h2>
                        <p class="text-xs text-slate-600">Organización de archivos escolares:</p>
                        <p class="text-xs text-slate-700 bg-white p-2 rounded border border-slate-200 mt-2">
                            Crea una carpeta por semestre en la nube de tu correo escolar. Evita trabajar en archivos locales sin respaldo para prevenir pérdidas si el equipo falla.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 5. SEGURIDAD Y BÚSQUEDAS -->
        <section id="tab-seguridad" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm">
                <div class="border-b border-slate-200 pb-4 mb-6">
                    <h1 class="text-2xl font-bold text-slate-900">Seguridad Digital y Operadores de Búsqueda</h1>
                    <p class="text-sm text-slate-600 mt-1">Técnicas de filtrado de datos en la web y prevención de riesgos informáticos.</p>
                </div>

                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Operadores de Búsqueda -->
                    <div class="space-y-3">
                        <h2 class="font-bold text-slate-900 text-sm flex items-center gap-2">
                            <i class="fa-solid fa-magnifying-glass text-rose-600"></i> Comandos para Filtrar en Google
                        </h2>

                        <div class="p-3 bg-slate-50 rounded-lg border border-slate-200 space-y-1">
                            <code class="font-mono text-xs text-rose-700 font-bold">filetype:pdf</code>
                            <p class="text-xs text-slate-600">Filtra exclusivamente documentos en formato PDF. <br><em class="text-slate-500 font-mono">Ejemplo: leyes de newton filetype:pdf</em></p>
                        </div>

                        <div class="p-3 bg-slate-50 rounded-lg border border-slate-200 space-y-1">
                            <code class="font-mono text-xs text-rose-700 font-bold">site:.edu ó site:.gob</code>
                            <p class="text-xs text-slate-600">Limita los resultados a dominios académicos o gubernamentales. <br><em class="text-slate-500 font-mono">Ejemplo: celula vegetal site:.edu.mx</em></p>
                        </div>

                        <div class="p-3 bg-slate-50 rounded-lg border border-slate-200 space-y-1">
                            <code class="font-mono text-xs text-rose-700 font-bold">"frase exacta entre comillas"</code>
                            <p class="text-xs text-slate-600">Busca el texto entrecomillado en ese orden específico sin omitir palabras.</p>
                        </div>
                    </div>

                    <!-- Ciberseguridad -->
                    <div class="space-y-3">
                        <h2 class="font-bold text-slate-900 text-sm flex items-center gap-2">
                            <i class="fa-solid fa-shield-cat text-rose-600"></i> Medidas de Protección Básicas
                        </h2>

                        <div class="p-3 bg-rose-50/60 rounded-lg border border-rose-100 text-xs text-slate-700 space-y-2">
                            <p><strong>Identificación de Phishing:</strong> No ingreses tus credenciales institucionales en enlaces recibidos por SMS o correos no verificados. Revisa que el dominio en la barra de direcciones sea exactamente el oficial.</p>
                            <p><strong>Verificación en dos pasos (2FA):</strong> Activa la confirmación en el celular para acceder a tus cuentas escolares y evitar accesos no autorizados.</p>
                            <p><strong>Contraseñas seguras:</strong> Evita fechas de nacimiento o secuencias simples. Combina más de 12 caracteres mezclando letras, números y símbolos.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 6. SOPORTE TÉCNICO -->
        <section id="tab-soporte" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm">
                <div class="border-b border-slate-200 pb-4 mb-6">
                    <h1 class="text-2xl font-bold text-slate-900">Soporte Técnico y Solución de Problemas</h1>
                    <p class="text-sm text-slate-600 mt-1">Procedimientos para resolver fallos comunes en software y sistema operativo.</p>
                </div>

                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Errores de Office y Sistema -->
                    <div class="space-y-4">
                        <h2 class="font-bold text-slate-900 text-sm border-b pb-2">Diagnóstico de Fallos Habituales</h2>

                        <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200 space-y-1 text-xs">
                            <span class="font-bold text-amber-800 block">Documento de Word cerrado sin guardar</span>
                            <p class="text-slate-600">Abre Word, dirígete a <code class="font-mono bg-slate-200 px-1 rounded">Archivo > Información > Administrar documento > Recuperar documentos no guardados</code> para buscar la copia temporal generada por el sistema.</p>
                        </div>

                        <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200 space-y-1 text-xs">
                            <span class="font-bold text-amber-800 block">Office bloqueado / Modo de lectura</span>
                            <p class="text-slate-600">Si las barras de herramientas aparecen deshabilitadas, la licencia caduco. Inicia sesión en la esquina superior derecha con tu correo institucional para activar la licencia de estudiante.</p>
                        </div>

                        <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200 space-y-1 text-xs">
                            <span class="font-bold text-amber-800 block">La computadora no responde / Programa congelado</span>
                            <p class="text-slate-600">Presiona la combinación <kbd class="font-mono bg-slate-200 px-1 border rounded">Ctrl + Shift + Esc</kbd> para abrir el Administrador de tareas, selecciona la aplicación bloqueada y haz clic en "Finalizar tarea".</p>
                        </div>
                    </div>

                    <!-- Errores de Excel -->
                    <div class="space-y-4">
                        <h2 class="font-bold text-slate-900 text-sm border-b pb-2">Significado de Errores en Excel</h2>

                        <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200 space-y-1 text-xs">
                            <span class="font-mono font-bold text-rose-700">#¡VALOR!</span>
                            <p class="text-slate-600">Ocurre cuando intentas hacer una operación matemática usando celdas que contienen texto en lugar de números.</p>
                        </div>

                        <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200 space-y-1 text-xs">
                            <span class="font-mono font-bold text-rose-700">#REF!</span>
                            <p class="text-slate-600">Indica que la celda que servía de referencia para la fórmula fue eliminada de la hoja de trabajo.</p>
                        </div>

                        <div class="p-3.5 bg-slate-50 rounded-lg border border-slate-200 space-y-1 text-xs">
                            <span class="font-mono font-bold text-rose-700">#¿NOMBRE?</span>
                            <p class="text-slate-600">Significa que la fórmula está mal escrita (ejemplo: escribir <code class="font-mono bg-slate-200 px-1 rounded">=PROMEDIOO</code> en lugar de <code class="font-mono bg-slate-200 px-1 rounded">=PROMEDIO</code>).</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 7. ATAJOS DE TECLADO -->
        <section id="tab-atajos" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm">
                <div class="border-b border-slate-200 pb-4 mb-6 flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4">
                    <div>
                        <h1 class="text-2xl font-bold text-slate-900">Tabla de Atajos de Teclado</h1>
                        <p class="text-sm text-slate-600 mt-1">Combinaciones clave para agilizar el trabajo en pantalla.</p>
                    </div>
                    <!-- Filtro -->
                    <div class="flex items-center gap-2">
                        <span class="text-xs font-semibold text-slate-500">Filtrar:</span>
                        <select id="shortcut-filter" onchange="filterShortcuts()" class="p-2 border border-slate-300 rounded-lg text-xs font-medium bg-slate-50">
                            <option value="all">Todos los programas</option>
                            <option value="win">Windows General</option>
                            <option value="word">Microsoft Word</option>
                            <option value="excel">Microsoft Excel</option>
                            <option value="ppt">PowerPoint</option>
                        </select>
                    </div>
                </div>

                <div class="overflow-x-auto">
                    <table class="w-full text-left text-xs text-slate-700 border-collapse">
                        <thead>
                            <tr class="bg-slate-100 border-b border-slate-200 text-slate-800 font-bold">
                                <th class="p-3">Acción / Función</th>
                                <th class="p-3">Combinación de Teclas</th>
                                <th class="p-3">Programa</th>
                            </tr>
                        </thead>
                        <tbody id="shortcut-tbody" class="divide-y divide-slate-200 font-mono">
                            <tr data-cat="win">
                                <td class="p-3 font-sans">Copiar selección</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">Ctrl + C</kbd></td>
                                <td class="p-3 font-sans text-slate-500">Windows / General</td>
                            </tr>
                            <tr data-cat="win">
                                <td class="p-3 font-sans">Pegar selección</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">Ctrl + V</kbd></td>
                                <td class="p-3 font-sans text-slate-500">Windows / General</td>
                            </tr>
                            <tr data-cat="win">
                                <td class="p-3 font-sans">Deshacer última acción</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">Ctrl + Z</kbd></td>
                                <td class="p-3 font-sans text-slate-500">Windows / General</td>
                            </tr>
                            <tr data-cat="win">
                                <td class="p-3 font-sans">Captura de pantalla parcial</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">Win + Shift + S</kbd></td>
                                <td class="p-3 font-sans text-slate-500">Windows General</td>
                            </tr>
                            <tr data-cat="word">
                                <td class="p-3 font-sans">Guardar documento activo</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">Ctrl + G</kbd></td>
                                <td class="p-3 font-sans text-blue-600 font-semibold">Word</td>
                            </tr>
                            <tr data-cat="word">
                                <td class="p-3 font-sans">Aplicar formato Negrita</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">Ctrl + N</kbd></td>
                                <td class="p-3 font-sans text-blue-600 font-semibold">Word</td>
                            </tr>
                            <tr data-cat="word">
                                <td class="p-3 font-sans">Justificar párrafo</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">Ctrl + J</kbd></td>
                                <td class="p-3 font-sans text-blue-600 font-semibold">Word</td>
                            </tr>
                            <tr data-cat="excel">
                                <td class="p-3 font-sans">Insertar Autosuma rápida</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">Alt + =</kbd></td>
                                <td class="p-3 font-sans text-emerald-600 font-semibold">Excel</td>
                            </tr>
                            <tr data-cat="excel">
                                <td class="p-3 font-sans">Buscar en la hoja actual</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">Ctrl + B</kbd></td>
                                <td class="p-3 font-sans text-emerald-600 font-semibold">Excel</td>
                            </tr>
                            <tr data-cat="ppt">
                                <td class="p-3 font-sans">Iniciar presentación desde inicio</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">F5</kbd></td>
                                <td class="p-3 font-sans text-orange-600 font-semibold">PowerPoint</td>
                            </tr>
                            <tr data-cat="ppt">
                                <td class="p-3 font-sans">Iniciar desde diapositiva actual</td>
                                <td class="p-3"><kbd class="bg-slate-100 border px-1.5 py-0.5 rounded">Shift + F5</kbd></td>
                                <td class="p-3 font-sans text-orange-600 font-semibold">PowerPoint</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </section>

        <!-- 8. RECURSOS EXTERNOS -->
        <section id="tab-recursos" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm">
                <div class="border-b border-slate-200 pb-4 mb-6">
                    <h1 class="text-2xl font-bold text-slate-900">Recursos Enlazados y Plataformas Utilitarias</h1>
                    <p class="text-sm text-slate-600 mt-1">Sitios web complementarios para desarrollo de proyectos académicos.</p>
                </div>

                <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-4">
                    <div class="p-4 bg-slate-50 border border-slate-200 rounded-lg space-y-2">
                        <span class="font-bold text-sm text-slate-900 block">Plantillas de Presentación</span>
                        <p class="text-xs text-slate-600">Descarga de diseños para PowerPoint y Google Slides.</p>
                        <div class="pt-2 text-xs font-mono text-sky-700 space-y-1">
                            <p>• slidesgo.com</p>
                            <p>• slidescarnival.com</p>
                        </div>
                    </div>

                    <div class="p-4 bg-slate-50 border border-slate-200 rounded-lg space-y-2">
                        <span class="font-bold text-sm text-slate-900 block">Bancos de Imágenes Libres</span>
                        <p class="text-xs text-slate-600">Fotografías de alta resolución sin derechos de autor.</p>
                        <div class="pt-2 text-xs font-mono text-sky-700 space-y-1">
                            <p>• unsplash.com</p>
                            <p>• pexels.com</p>
                        </div>
                    </div>

                    <div class="p-4 bg-slate-50 border border-slate-200 rounded-lg space-y-2">
                        <span class="font-bold text-sm text-slate-900 block">Edición de PDF</span>
                        <p class="text-xs text-slate-600">Herramientas para unir, dividir o comprimir archivos PDF.</p>
                        <div class="pt-2 text-xs font-mono text-sky-700 space-y-1">
                            <p>• ilovepdf.com</p>
                            <p>• smallpdf.com</p>
                        </div>
                    </div>

                    <div class="p-4 bg-slate-50 border border-slate-200 rounded-lg space-y-2">
                        <span class="font-bold text-sm text-slate-900 block">Generador de Citas APA</span>
                        <p class="text-xs text-slate-600">Creación automática de fichas bibliográficas.</p>
                        <div class="pt-2 text-xs font-mono text-sky-700 space-y-1">
                            <p>• scribbr.es/detector-de-plagio/generador-apa</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 9. PREGUNTAS FRECUENTES -->
        <section id="tab-faq" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm">
                <div class="border-b border-slate-200 pb-4 mb-6">
                    <h1 class="text-2xl font-bold text-slate-900">Preguntas Frecuentes (FAQ)</h1>
                    <p class="text-sm text-slate-600 mt-1">Dudas habituales sobre plataformas escolares y trámites informáticos.</p>
                </div>

                <div class="space-y-4 text-xs sm:text-sm">
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200">
                        <h2 class="font-bold text-slate-900 mb-1">¿Cómo descargar Microsoft Office gratis con la cuenta de la escuela?</h2>
                        <p class="text-slate-600">Entra a <code class="font-mono bg-slate-200 px-1 rounded">office.com</code> e ingresa tu correo institucional completo con tu contraseña. En la pantalla principal ubica el botón "Instalar Office" en la esquina superior derecha para descargar el instalador oficial.</p>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200">
                        <h2 class="font-bold text-slate-900 mb-1">¿Qué hacer si un archivo reasa el tamaño máximo permitido en Google Classroom o Teams?</h2>
                        <p class="text-slate-600">Sube el archivo a tu unidad personal de Google Drive o OneDrive. Una vez arriba, cambia los permisos a "Cualquier persona con el enlace puede ver" y pega el link directo en el apartado de la entrega de la tarea.</p>
                    </div>

                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200">
                        <h2 class="font-bold text-slate-900 mb-1">¿Cuándo conviene entregar en PDF y cuándo en DOCX o PPTX?</h2>
                        <p class="text-slate-600">Entrega en **PDF** en todos los ensayos, reportes y tareas finales para congelar el formato y evitar que las imágenes o el texto se desacomoden al abrirse en la computadora del profesor. Usa **.DOCX** o **.PPTX** únicamente cuando te pidan un trabajo editable.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 10. EXAMEN / QUIZ (10 PREGUNTAS PRACTICAS) -->
        <section id="tab-quiz" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm">
                <div class="border-b border-slate-200 pb-4 mb-6 flex flex-col sm:flex-row justify-between items-start sm:items-center gap-2">
                    <div>
                        <h1 class="text-2xl font-bold text-slate-900">Examen de Evaluación de Conocimientos</h1>
                        <p class="text-sm text-slate-600 mt-1">Prueba práctica de 10 reactivos sobre las herramientas trabajadas.</p>
                    </div>
                    <div class="bg-slate-900 text-white font-mono px-4 py-2 rounded-lg text-xs font-bold">
                        Aciertos: <span id="quiz-score" class="text-emerald-400 text-sm">0</span> / 10
                    </div>
                </div>

                <form id="exam-form" class="space-y-6">
                    <!-- Q1 -->
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2 text-xs sm:text-sm">
                        <p class="font-bold text-slate-900">1. ¿Cuál es el margen estándar requerido por las normas APA 7.ª edición?</p>
                        <div class="space-y-1.5 font-normal">
                            <label class="flex items-center gap-2"><input type="radio" name="q1" value="a"> 3.0 cm superior e inferior</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q1" value="b"> 2.54 cm (1 pulgada) en los 4 lados</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q1" value="c"> Margen estrecho de 1.27 cm</label>
                        </div>
                    </div>

                    <!-- Q2 -->
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2 text-xs sm:text-sm">
                        <p class="font-bold text-slate-900">2. ¿Qué función debes asignar a un texto en Word para que aparezca automáticamente en la Tabla de contenido?</p>
                        <div class="space-y-1.5 font-normal">
                            <label class="flex items-center gap-2"><input type="radio" name="q2" value="a"> Negrita y Subrayado</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q2" value="b"> Estilos Título 1 o Título 2</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q2" value="c"> Texto en mayúsculas</label>
                        </div>
                    </div>

                    <!-- Q3 -->
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2 text-xs sm:text-sm">
                        <p class="font-bold text-slate-900">3. ¿Qué fórmula de Excel se usa para obtener la media aritmética de un rango numérico?</p>
                        <div class="space-y-1.5 font-normal">
                            <label class="flex items-center gap-2"><input type="radio" name="q3" value="a"> =PROMEDIO()</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q3" value="b"> =SUMA()</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q3" value="c"> =MEDIA()</label>
                        </div>
                    </div>

                    <!-- Q4 -->
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2 text-xs sm:text-sm">
                        <p class="font-bold text-slate-900">4. Si en una celda de Excel aparece el error #¡VALOR!, ¿cuál es la causa principal?</p>
                        <div class="space-y-1.5 font-normal">
                            <label class="flex items-center gap-2"><input type="radio" name="q4" value="a"> Se escribió mal el nombre de la fórmula</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q4" value="b"> Se intentó hacer una operación matemática usando celdas con texto</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q4" value="c"> La columna es muy angosta para mostrar el número</label>
                        </div>
                    </div>

                    <!-- Q5 -->
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2 text-xs sm:text-sm">
                        <p class="font-bold text-slate-900">5. ¿En qué consiste la regla 6x6 recomendada para las presentaciones de PowerPoint?</p>
                        <div class="space-y-1.5 font-normal">
                            <label class="flex items-center gap-2"><input type="radio" name="q5" value="a"> Máximo 6 diapositivas expuestas en 6 minutos</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q5" value="b"> Máximo 6 líneas por diapositiva y máximo 6 palabras por línea</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q5" value="c"> Usar 6 imágenes y 6 colores diferentes</label>
                        </div>
                    </div>

                    <!-- Q6 -->
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2 text-xs sm:text-sm">
                        <p class="font-bold text-slate-900">6. Al compartir un archivo en la nube, ¿qué permiso debes asignar si quieres que la otra persona NO pueda modificar el contenido?</p>
                        <div class="space-y-1.5 font-normal">
                            <label class="flex items-center gap-2"><input type="radio" name="q6" value="a"> Editor</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q6" value="b"> Lector</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q6" value="c"> Propietario</label>
                        </div>
                    </div>

                    <!-- Q7 -->
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2 text-xs sm:text-sm">
                        <p class="font-bold text-slate-900">7. ¿Qué comando de búsqueda debes escribir en Google para encontrar únicamente archivos PDF sobre la Célula?</p>
                        <div class="space-y-1.5 font-normal">
                            <label class="flex items-center gap-2"><input type="radio" name="q7" value="a"> la celula filetype:pdf</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q7" value="b"> la celula site:pdf</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q7" value="c"> "la celula" search:pdf</label>
                        </div>
                    </div>

                    <!-- Q8 -->
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2 text-xs sm:text-sm">
                        <p class="font-bold text-slate-900">8. Si cerraste Word por accidente sin guardar tu progreso, ¿en qué apartado buscas la copia temporal?</p>
                        <div class="space-y-1.5 font-normal">
                            <label class="flex items-center gap-2"><input type="radio" name="q8" value="a"> En la Papelera de reciclaje</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q8" value="b"> En Archivo > Información > Recuperar documentos no guardados</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q8" value="c"> En la pestaña Vista > Cambiar ventanas</label>
                        </div>
                    </div>

                    <!-- Q9 -->
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2 text-xs sm:text-sm">
                        <p class="font-bold text-slate-900">9. ¿Cuál es la combinación de teclas para guardar un documento de Word rápidamente?</p>
                        <div class="space-y-1.5 font-normal">
                            <label class="flex items-center gap-2"><input type="radio" name="q9" value="a"> Ctrl + S</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q9" value="b"> Ctrl + G</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q9" value="c"> Alt + F4</label>
                        </div>
                    </div>

                    <!-- Q10 -->
                    <div class="p-4 bg-slate-50 rounded-lg border border-slate-200 space-y-2 text-xs sm:text-sm">
                        <p class="font-bold text-slate-900">10. ¿Cuál es el atajo en Windows para realizar una captura de pantalla seleccionando solo una zona específica?</p>
                        <div class="space-y-1.5 font-normal">
                            <label class="flex items-center gap-2"><input type="radio" name="q10" value="a"> Win + Shift + S</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q10" value="b"> Ctrl + ImpPnt</label>
                            <label class="flex items-center gap-2"><input type="radio" name="q10" value="c"> Alt + F12</label>
                        </div>
                    </div>

                    <div class="flex gap-3 pt-2">
                        <button type="button" onclick="gradeExam()" class="bg-sky-600 hover:bg-sky-500 text-white font-bold text-xs px-5 py-2.5 rounded-lg transition">
                            Evaluar Respuestas
                        </button>
                        <button type="button" onclick="resetExam()" class="bg-slate-200 hover:bg-slate-300 text-slate-700 font-semibold text-xs px-4 py-2.5 rounded-lg transition">
                            Reiniciar Examen
                        </button>
                    </div>
                </form>

                <!-- Feedback Area -->
                <div id="exam-feedback" class="hidden mt-6 p-4 rounded-lg border text-xs sm:text-sm"></div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-navy-950 text-slate-400 text-xs py-6 border-t border-slate-800 mt-auto">
        <div class="max-w-7xl mx-auto px-4 text-center">
            <p>Guía de Informática Básica para Educación Media Superior. Contenido estructurado para estudio académico.</p>
        </div>
    </footer>

    <!-- Logic Javascript -->
    <script>
        // Tab Handler
        function switchTab(tabId) {
            const contents = document.querySelectorAll('.tab-content');
            contents.forEach(el => el.classList.add('hidden'));

            const buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(btn => btn.classList.remove('active'));

            const targetContent = document.getElementById('tab-' + tabId);
            if (targetContent) {
                targetContent.classList.remove('hidden');
            }

            const targetBtn = document.getElementById('btn-' + tabId);
            if (targetBtn) {
                targetBtn.classList.add('active');
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Excel Simulator JS Logic
        function runExcelSim() {
            const m1 = parseFloat(document.getElementById('sim-m1').value) || 0;
            const m2 = parseFloat(document.getElementById('sim-m2').value) || 0;
            const m3 = parseFloat(document.getElementById('sim-m3').value) || 0;
            const m4 = parseFloat(document.getElementById('sim-m4').value) || 0;

            const weightPercent = parseFloat(document.getElementById('sim-weight').value);
            const examVal = parseFloat(document.getElementById('sim-exam').value) || 0;

            document.getElementById('lbl-weight').innerText = weightPercent + "%";

            // PROMEDIO Parciales
            const avgParcial = (m1 + m2 + m3 + m4) / 4;
            document.getElementById('out-avg-parcial').innerText = avgParcial.toFixed(2);

            // Weights
            const wParcial = (100 - weightPercent) / 100;
            const wExam = weightPercent / 100;

            document.getElementById('out-p-weight').innerText = avgParcial.toFixed(2);
            document.getElementById('out-w1').innerText = wParcial.toFixed(2);
            document.getElementById('out-e-val').innerText = examVal.toFixed(1);
            document.getElementById('out-w2').innerText = wExam.toFixed(2);

            // Final Formula
            const finalScore = (avgParcial * wParcial) + (examVal * wExam);
            const formattedScore = finalScore.toFixed(2);

            document.getElementById('out-final-val').innerText = formattedScore;
            document.getElementById('out-score').innerText = formattedScore;

            const badge = document.getElementById('out-badge');
            if (finalScore >= 6.0) {
                badge.innerText = "Estatus: APROBADO";
                badge.className = "px-3 py-1 rounded-full text-xs font-bold bg-emerald-500/20 text-emerald-300 border border-emerald-500/30";
                document.getElementById('out-score').className = "text-5xl font-extrabold text-emerald-400 font-mono";
            } else {
                badge.innerText = "Estatus: EXTRAORDINARIO";
                badge.className = "px-3 py-1 rounded-full text-xs font-bold bg-rose-500/20 text-rose-300 border border-rose-500/30";
                document.getElementById('out-score').className = "text-5xl font-extrabold text-rose-400 font-mono";
            }
        }

        function resetSim() {
            document.getElementById('sim-m1').value = 8;
            document.getElementById('sim-m2').value = 7.5;
            document.getElementById('sim-m3').value = 9;
            document.getElementById('sim-m4').value = 6;
            document.getElementById('sim-weight').value = 40;
            document.getElementById('sim-exam').value = 8.5;
            runExcelSim();
        }

        // Shortcuts Table Filter
        function filterShortcuts() {
            const filterVal = document.getElementById('shortcut-filter').value;
            const rows = document.querySelectorAll('#shortcut-tbody tr');

            rows.forEach(row => {
                const category = row.getAttribute('data-cat');
                if (filterVal === 'all' || category === filterVal) {
                    row.style.display = '';
                } else {
                    row.style.display = 'none';
                }
            });
        }

        // Exam Evaluation Logic
        const answerKey = {
            q1: 'b',
            q2: 'b',
            q3: 'a',
            q4: 'b',
            q5: 'b',
            q6: 'b',
            q7: 'a',
            q8: 'b',
            q9: 'b',
            q10: 'a'
        };

        function gradeExam() {
            const form = document.getElementById('exam-form');
            let score = 0;
            const total = 10;

            for (let i = 1; i <= total; i++) {
                const selected = form.querySelector(`input[name="q${i}"]:checked`);
                if (selected && selected.value === answerKey[`q${i}`]) {
                    score++;
                }
            }

            document.getElementById('quiz-score').innerText = score;
            const feedback = document.getElementById('exam-feedback');
            feedback.classList.remove('hidden');

            if (score >= 8) {
                feedback.className = "mt-6 p-4 rounded-lg border text-xs sm:text-sm bg-emerald-50 border-emerald-200 text-emerald-900";
                feedback.innerHTML = `<strong>Calificación: ${score} / 10 (Aprobado)</strong><br>Demuestras dominio de los conceptos esenciales de informática e instrumentos de ofimática.`;
            } else if (score >= 6) {
                feedback.className = "mt-6 p-4 rounded-lg border text-xs sm:text-sm bg-amber-50 border-amber-200 text-amber-900";
                feedback.innerHTML = `<strong>Calificación: ${score} / 10 (Suficiente)</strong><br>Aprobaste la evaluación básica, pero se recomienda repasar los módulos de atajos y errores comunes de Excel.`;
            } else {
                feedback.className = "mt-6 p-4 rounded-lg border text-xs sm:text-sm bg-rose-50 border-rose-200 text-rose-900";
                feedback.innerHTML = `<strong>Calificación: ${score} / 10 (No Aprobado)</strong><br>Revisa nuevamente el contenido de las pestañas temáticas antes de presentar la prueba.`;
            }
        }

        function resetExam() {
            document.getElementById('exam-form').reset();
            document.getElementById('quiz-score').innerText = "0";
            document.getElementById('exam-feedback').classList.add('hidden');
        }

        // Init
        window.onload = function() {
            runExcelSim();
        };
    </script>
</body>
</html>
