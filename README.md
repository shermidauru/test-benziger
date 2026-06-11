[index_1.html](https://github.com/user-attachments/files/28841947/index_1.html)
# test-benziger
Test de Bezinger 
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Test de Perfil Benziger</title>
<style>
  :root {
    --fl: #2563EB;   /* Frontal Izquierdo - Azul */
    --fr: #7C3AED;   /* Frontal Derecho - Violeta */
    --bl: #059669;   /* Basal Izquierdo - Verde */
    --br: #D97706;   /* Basal Derecho - Naranja */
    --bg: #F8FAFC;
    --card: #FFFFFF;
    --text: #1E293B;
    --sub: #64748B;
    --border: #E2E8F0;
    --radius: 12px;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Segoe UI', system-ui, sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
  }

  header {
    background: linear-gradient(135deg, #1E293B 0%, #334155 100%);
    color: white;
    padding: 32px 24px 24px;
    text-align: center;
  }
  header h1 { font-size: 1.8rem; font-weight: 700; letter-spacing: -0.5px; }
  header p  { color: #94A3B8; margin-top: 6px; font-size: 0.95rem; }

  .progress-bar {
    background: #334155;
    height: 6px;
    width: 100%;
  }
  .progress-fill {
    height: 100%;
    background: linear-gradient(90deg, #2563EB, #7C3AED);
    transition: width 0.4s ease;
  }

  main { max-width: 680px; margin: 0 auto; padding: 24px 16px 48px; }

  /* ── Intro ── */
  #intro { text-align: center; padding: 24px 0; }
  #intro h2 { font-size: 1.4rem; color: var(--text); margin-bottom: 12px; }
  #intro p  { color: var(--sub); line-height: 1.7; margin-bottom: 8px; font-size: 0.95rem; }
  .brain-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin: 24px 0;
    text-align: left;
  }
  .brain-card {
    border-radius: 10px;
    padding: 14px 16px;
    border-left: 4px solid;
  }
  .brain-card.fl { background: #EFF6FF; border-color: var(--fl); }
  .brain-card.fr { background: #F5F3FF; border-color: var(--fr); }
  .brain-card.bl { background: #ECFDF5; border-color: var(--bl); }
  .brain-card.br { background: #FFFBEB; border-color: var(--br); }
  .brain-card h4 { font-size: 0.85rem; font-weight: 700; margin-bottom: 4px; }
  .brain-card.fl h4 { color: var(--fl); }
  .brain-card.fr h4 { color: var(--fr); }
  .brain-card.bl h4 { color: var(--bl); }
  .brain-card.br h4 { color: var(--br); }
  .brain-card p  { font-size: 0.82rem; color: var(--sub); line-height: 1.5; }

  .btn-start {
    background: linear-gradient(135deg, #1E293B, #334155);
    color: white;
    border: none;
    padding: 14px 40px;
    border-radius: 8px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    margin-top: 8px;
    transition: transform 0.15s, opacity 0.15s;
  }
  .btn-start:hover { transform: translateY(-2px); opacity: 0.9; }

  /* ── Questions ── */
  #quiz { display: none; }

  .q-counter {
    font-size: 0.82rem;
    color: var(--sub);
    font-weight: 600;
    letter-spacing: 0.5px;
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .q-text {
    font-size: 1.15rem;
    font-weight: 600;
    color: var(--text);
    line-height: 1.5;
    margin-bottom: 20px;
  }

  .options { display: flex; flex-direction: column; gap: 10px; }

  .opt-btn {
    background: var(--card);
    border: 2px solid var(--border);
    border-radius: 10px;
    padding: 14px 18px;
    text-align: left;
    font-size: 0.95rem;
    color: var(--text);
    cursor: pointer;
    transition: all 0.18s ease;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .opt-btn:hover { border-color: #94A3B8; background: #F1F5F9; transform: translateX(4px); }
  .opt-btn.selected { border-color: #334155; background: #F8FAFC; font-weight: 600; }
  .opt-letter {
    width: 28px; height: 28px;
    border-radius: 50%;
    background: #E2E8F0;
    display: flex; align-items: center; justify-content: center;
    font-size: 0.8rem; font-weight: 700; color: var(--sub);
    flex-shrink: 0;
  }
  .opt-btn.selected .opt-letter { background: #334155; color: white; }

  .nav-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 24px;
  }
  .btn-nav {
    padding: 10px 24px;
    border-radius: 8px;
    font-size: 0.95rem;
    font-weight: 600;
    cursor: pointer;
    border: none;
    transition: all 0.15s;
  }
  .btn-prev { background: var(--border); color: var(--text); }
  .btn-prev:hover { background: #CBD5E1; }
  .btn-next { background: #1E293B; color: white; }
  .btn-next:hover { background: #334155; }
  .btn-next:disabled { background: #CBD5E1; cursor: not-allowed; }

  /* ── Results ── */
  #results { display: none; }

  .result-header {
    text-align: center;
    padding: 24px 0 16px;
  }
  .result-header h2 { font-size: 1.4rem; font-weight: 700; }
  .result-header p  { color: var(--sub); margin-top: 6px; }

  .winner-card {
    border-radius: var(--radius);
    padding: 24px;
    margin: 20px 0;
    text-align: center;
    border: 3px solid;
  }
  .winner-card h3 { font-size: 1.5rem; font-weight: 800; margin-bottom: 6px; }
  .winner-card .tagline { font-size: 1rem; opacity: 0.85; margin-bottom: 12px; }
  .winner-card p  { font-size: 0.92rem; line-height: 1.7; }

  .winner-card.fl { background: #EFF6FF; border-color: var(--fl); color: var(--fl); }
  .winner-card.fr { background: #F5F3FF; border-color: var(--fr); color: var(--fr); }
  .winner-card.bl { background: #ECFDF5; border-color: var(--bl); color: var(--bl); }
  .winner-card.br { background: #FFFBEB; border-color: var(--br); color: var(--br); }
  .winner-card p  { color: var(--text); }

  .score-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin: 20px 0;
  }
  .score-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px;
    display: flex;
    flex-direction: column;
    gap: 6px;
  }
  .score-label { font-size: 0.8rem; font-weight: 700; }
  .score-label.fl { color: var(--fl); }
  .score-label.fr { color: var(--fr); }
  .score-label.bl { color: var(--bl); }
  .score-label.br { color: var(--br); }
  .score-bar-bg { background: #E2E8F0; border-radius: 4px; height: 8px; }
  .score-bar    { border-radius: 4px; height: 8px; transition: width 0.6s ease; }
  .score-bar.fl { background: var(--fl); }
  .score-bar.fr { background: var(--fr); }
  .score-bar.bl { background: var(--bl); }
  .score-bar.br { background: var(--br); }
  .score-val { font-size: 0.85rem; font-weight: 600; color: var(--sub); }

  .traits-section { margin: 20px 0; }
  .traits-section h4 { font-size: 1rem; font-weight: 700; margin-bottom: 12px; color: var(--text); }
  .traits-grid { display: flex; flex-wrap: wrap; gap: 8px; }
  .trait-chip {
    padding: 6px 14px;
    border-radius: 20px;
    font-size: 0.82rem;
    font-weight: 600;
    border: 1.5px solid;
  }
  .trait-chip.fl { background: #EFF6FF; border-color: var(--fl); color: var(--fl); }
  .trait-chip.fr { background: #F5F3FF; border-color: var(--fr); color: var(--fr); }
  .trait-chip.bl { background: #ECFDF5; border-color: var(--bl); color: var(--bl); }
  .trait-chip.br { background: #FFFBEB; border-color: var(--br); color: var(--br); }

  .roles-section { background: var(--card); border: 1px solid var(--border); border-radius: var(--radius); padding: 20px; margin: 16px 0; }
  .roles-section h4 { font-size: 0.95rem; font-weight: 700; margin-bottom: 10px; }
  .roles-section ul { list-style: none; display: flex; flex-direction: column; gap: 6px; }
  .roles-section li { font-size: 0.9rem; color: var(--sub); display: flex; align-items: center; gap: 8px; }
  .roles-section li::before { content: "▸"; font-weight: 700; }

  .warning-box {
    background: #FFF7ED;
    border: 1px solid #FED7AA;
    border-radius: 10px;
    padding: 16px;
    margin: 16px 0;
    font-size: 0.88rem;
    color: #92400E;
    line-height: 1.6;
  }
  .warning-box strong { color: #78350F; }

  .btn-restart {
    width: 100%;
    padding: 14px;
    background: #1E293B;
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    margin-top: 8px;
  }
  .btn-restart:hover { background: #334155; }
</style>
</head>
<body>

<header>
  <h1>🧠 Test de Perfil Benziger</h1>
  <p>Descubrí tu estilo natural de pensar y trabajar</p>
</header>
<div class="progress-bar"><div class="progress-fill" id="progressFill" style="width:0%"></div></div>

<main>

<!-- INTRO -->
<div id="intro">
  <h2>¿Cómo pensás naturalmente?</h2>
  <p>La teoría de Katherine Benziger identifica cuatro modos de pensamiento basados en las áreas del cerebro que cada persona usa con mayor facilidad y eficiencia.</p>
  <p>Este test tiene <strong>20 preguntas</strong> y tarda unos <strong>5 minutos</strong>. No hay respuestas correctas ni incorrectas.</p>

  <div class="brain-grid">
    <div class="brain-card fl">
      <h4>🔵 Frontal Izquierdo</h4>
      <p>Lógico, analítico, orientado a resultados y datos.</p>
    </div>
    <div class="brain-card fr">
      <h4>🟣 Frontal Derecho</h4>
      <p>Creativo, visionario, intuitivo, orientado al futuro.</p>
    </div>
    <div class="brain-card bl">
      <h4>🟢 Basal Izquierdo</h4>
      <p>Organizado, metódico, confiable, orientado al proceso.</p>
    </div>
    <div class="brain-card br">
      <h4>🟠 Basal Derecho</h4>
      <p>Empático, comunicativo, orientado a las personas.</p>
    </div>
  </div>

  <button class="btn-start" onclick="startQuiz()">Comenzar el Test →</button>
</div>

<!-- QUIZ -->
<div id="quiz">
  <div class="q-counter" id="qCounter">Pregunta 1 de 20</div>
  <div class="q-text" id="qText"></div>
  <div class="options" id="options"></div>
  <div class="nav-row">
    <button class="btn-nav btn-prev" id="btnPrev" onclick="prevQ()">← Anterior</button>
    <button class="btn-nav btn-next" id="btnNext" onclick="nextQ()" disabled>Siguiente →</button>
  </div>
</div>

<!-- RESULTS -->
<div id="results">
  <div class="result-header">
    <h2>Tu Perfil Benziger</h2>
    <p>Basado en tus respuestas</p>
  </div>
  <div id="winnerCard"></div>
  <div class="score-grid" id="scoreGrid"></div>
  <div class="traits-section">
    <h4>🎯 Tus fortalezas naturales</h4>
    <div class="traits-grid" id="traitsGrid"></div>
  </div>
  <div class="roles-section" id="rolesSection"></div>
  <div class="warning-box">
    <strong>⚠️ Importante:</strong> Este test es una herramienta orientativa para la reflexión y el autoconocimiento. No reemplaza una evaluación profesional certificada de Benziger. Los resultados buscan generar conversación y conciencia sobre los estilos de pensamiento, no etiquetar a las personas.
  </div>
  <button class="btn-restart" onclick="restart()">🔄 Reiniciar el Test</button>
</div>

</main>

<script>
// FL = Frontal Izquierdo, FR = Frontal Derecho, BL = Basal Izquierdo, BR = Basal Derecho
const questions = [
  {
    text: "Cuando tenés que resolver un problema complejo, preferís...",
    opts: [
      { text: "Analizar los datos y buscar la solución más lógica", type: "fl" },
      { text: "Explorar ideas creativas y pensar en soluciones novedosas", type: "fr" },
      { text: "Seguir un proceso paso a paso que ya funcionó antes", type: "bl" },
      { text: "Hablar con otras personas y construir una solución en equipo", type: "br" },
    ]
  },
  {
    text: "En una reunión de trabajo, tu rol más natural es...",
    opts: [
      { text: "Presentar argumentos con datos y lógica clara", type: "fl" },
      { text: "Proponer ideas innovadoras y visiones a largo plazo", type: "fr" },
      { text: "Tomar notas y asegurarte de que se definan los próximos pasos", type: "bl" },
      { text: "Mediar entre opiniones y cuidar el clima del grupo", type: "br" },
    ]
  },
  {
    text: "¿Qué te genera más satisfacción profesional?",
    opts: [
      { text: "Alcanzar resultados medibles y concretos", type: "fl" },
      { text: "Crear algo nuevo que no existía antes", type: "fr" },
      { text: "Completar tareas con precisión y dentro del plazo", type: "bl" },
      { text: "Ayudar a que mi equipo crezca y se desarrolle", type: "br" },
    ]
  },
  {
    text: "Cuando recibís información nueva, lo primero que hacés es...",
    opts: [
      { text: "Buscar si es consistente, lógica y está respaldada por evidencia", type: "fl" },
      { text: "Imaginar cómo podría aplicarse o transformarse en algo útil", type: "fr" },
      { text: "Clasificarla y organizarla en categorías o sistemas", type: "bl" },
      { text: "Pensar en cómo impacta en las personas involucradas", type: "br" },
    ]
  },
  {
    text: "¿Cómo preferís que te evalúen en tu trabajo?",
    opts: [
      { text: "Por los resultados objetivos que logré", type: "fl" },
      { text: "Por el impacto de mis ideas y propuestas", type: "fr" },
      { text: "Por mi confiabilidad y consistencia en el tiempo", type: "bl" },
      { text: "Por la calidad de mis relaciones y trabajo en equipo", type: "br" },
    ]
  },
  {
    text: "Cuando tenés que comunicar algo importante, preferís hacerlo con...",
    opts: [
      { text: "Un informe estructurado con datos y gráficos", type: "fl" },
      { text: "Una presentación visual o narrativa inspiradora", type: "fr" },
      { text: "Un procedimiento o manual paso a paso", type: "bl" },
      { text: "Una conversación cara a cara o en grupo", type: "br" },
    ]
  },
  {
    text: "¿Qué tipo de proyecto te motiva más?",
    opts: [
      { text: "Resolver un problema técnico complejo con métricas claras", type: "fl" },
      { text: "Diseñar una estrategia o visión de futuro para la organización", type: "fr" },
      { text: "Implementar un sistema que mejore la eficiencia operativa", type: "bl" },
      { text: "Desarrollar un programa de capacitación para el equipo", type: "br" },
    ]
  },
  {
    text: "Ante un cambio inesperado en el trabajo, tu primera reacción es...",
    opts: [
      { text: "Evaluar el impacto racionalmente antes de actuar", type: "fl" },
      { text: "Ver la oportunidad que puede traer el cambio", type: "fr" },
      { text: "Preocuparte por cómo afecta los procesos establecidos", type: "bl" },
      { text: "Consultar con el equipo para entender cómo se sienten", type: "br" },
    ]
  },
  {
    text: "En tu tiempo libre, ¿qué actividades disfrutás más?",
    opts: [
      { text: "Leer sobre tecnología, ciencia o análisis de datos", type: "fl" },
      { text: "Arte, música, viajes o explorar ideas filosóficas", type: "fr" },
      { text: "Cocinar siguiendo recetas, coleccionar o actividades de precisión", type: "bl" },
      { text: "Reunirte con amigos y familia, actividades solidarias", type: "br" },
    ]
  },
  {
    text: "¿Cuál de estas frases te representa mejor?",
    opts: [
      { text: "\"Los números no mienten — la evidencia manda\"", type: "fl" },
      { text: "\"El límite es la imaginación\"", type: "fr" },
      { text: "\"Si no está escrito, no existe\"", type: "bl" },
      { text: "\"La gente es lo más importante\"", type: "br" },
    ]
  },
  {
    text: "Cuando alguien del equipo comete un error, tu tendencia es...",
    opts: [
      { text: "Analizar qué falló y cómo prevenirlo con datos", type: "fl" },
      { text: "Ver si hay una forma creativa de convertirlo en aprendizaje", type: "fr" },
      { text: "Revisar el proceso para encontrar el punto de falla", type: "bl" },
      { text: "Hablar con la persona, entender cómo está y apoyarla", type: "br" },
    ]
  },
  {
    text: "¿Qué te resulta más difícil tolerar en el trabajo?",
    opts: [
      { text: "Decisiones sin fundamento lógico ni datos", type: "fl" },
      { text: "Rutinas repetitivas que no permiten creatividad", type: "fr" },
      { text: "El caos, la falta de orden y los procedimientos incumplidos", type: "bl" },
      { text: "Los conflictos interpersonales y los ambientes hostiles", type: "br" },
    ]
  },
  {
    text: "¿Cómo tomás tus decisiones más importantes?",
    opts: [
      { text: "Con análisis racional, comparando opciones y sus consecuencias", type: "fl" },
      { text: "Siguiendo mi intuición y visión de hacia dónde ir", type: "fr" },
      { text: "Consultando procedimientos, normas o experiencias pasadas", type: "bl" },
      { text: "Considerando el impacto en las personas involucradas", type: "br" },
    ]
  },
  {
    text: "En una negociación, tu punto fuerte es...",
    opts: [
      { text: "Argumentar con lógica y datos irrefutables", type: "fl" },
      { text: "Plantear una visión atractiva que inspire a la otra parte", type: "fr" },
      { text: "Ser meticuloso con los detalles del acuerdo", type: "bl" },
      { text: "Generar confianza y empatía con el otro", type: "br" },
    ]
  },
  {
    text: "¿Cómo aprendés mejor?",
    opts: [
      { text: "Leyendo, analizando casos y estudiando teorías", type: "fl" },
      { text: "Explorando, experimentando y conectando ideas", type: "fr" },
      { text: "Practicando con instrucciones claras paso a paso", type: "bl" },
      { text: "Aprendiendo con otros, en grupo o con un mentor", type: "br" },
    ]
  },
  {
    text: "¿Qué rol preferís asumir en un proyecto nuevo?",
    opts: [
      { text: "Líder técnico: diseñar la arquitectura y las métricas", type: "fl" },
      { text: "Visionario: definir el concepto y la estrategia", type: "fr" },
      { text: "Coordinador: organizar tareas, plazos y recursos", type: "bl" },
      { text: "Facilitador: asegurar que el equipo funcione bien", type: "br" },
    ]
  },
  {
    text: "¿Cuál describe mejor tu estilo de liderazgo?",
    opts: [
      { text: "Oriento al equipo con objetivos claros y métricas de rendimiento", type: "fl" },
      { text: "Inspiro al equipo con una visión y los invito a innovar", type: "fr" },
      { text: "Establezco procesos claros y me aseguro de cumplirlos", type: "bl" },
      { text: "Escucho a cada persona y adapto mi liderazgo a sus necesidades", type: "br" },
    ]
  },
  {
    text: "¿Qué valoran más en vos tus colegas?",
    opts: [
      { text: "Tu capacidad de análisis y resolución de problemas", type: "fl" },
      { text: "Tu creatividad y visión estratégica", type: "fr" },
      { text: "Tu confiabilidad y atención al detalle", type: "bl" },
      { text: "Tu calidez humana y habilidad para escuchar", type: "br" },
    ]
  },
  {
    text: "Cuando describís tu trabajo ideal, ¿qué aparece primero?",
    opts: [
      { text: "Desafíos intelectuales complejos con impacto medible", type: "fl" },
      { text: "Libertad para crear e innovar sin límites preestablecidos", type: "fr" },
      { text: "Claridad en las responsabilidades y procesos bien definidos", type: "bl" },
      { text: "Un equipo comprometido y un buen clima de trabajo", type: "br" },
    ]
  },
  {
    text: "¿Qué te describe mejor al final de un proyecto exitoso?",
    opts: [
      { text: "Siento satisfacción al ver los resultados concretos y medibles", type: "fl" },
      { text: "Me pregunto qué idea nueva puedo explorar a partir de esto", type: "fr" },
      { text: "Me aseguro de documentar todo para futuros proyectos", type: "bl" },
      { text: "Celebro con el equipo y reconozco el aporte de cada uno", type: "br" },
    ]
  },
];

const profiles = {
  fl: {
    name: "Frontal Izquierdo",
    emoji: "🔵",
    tagline: "El Analítico",
    desc: "Sos una persona lógica, orientada a resultados y al pensamiento crítico. Tomás decisiones basadas en datos y evidencias. Te destacás en entornos donde se valoran la precisión, la eficiencia y la racionalidad.",
    traits: ["Analítico", "Lógico", "Orientado a resultados", "Crítico", "Estratégico", "Objetivo", "Sistemático"],
    roles: ["Director de operaciones", "Gerente financiero", "Ingeniero", "Analista de datos", "Jefe de proyectos técnicos"],
    cls: "fl"
  },
  fr: {
    name: "Frontal Derecho",
    emoji: "🟣",
    tagline: "El Visionario",
    desc: "Sos creativo, intuitivo y orientado al futuro. Te energizás con las ideas, la innovación y la posibilidad de transformar la realidad. Sos capaz de ver conexiones que otros no ven y de inspirar a los demás con tu visión.",
    traits: ["Creativo", "Visionario", "Intuitivo", "Innovador", "Estratega", "Inspirador", "Conceptual"],
    roles: ["Director de innovación", "Gerente de marketing", "Consultor estratégico", "Diseñador", "Emprendedor"],
    cls: "fr"
  },
  bl: {
    name: "Basal Izquierdo",
    emoji: "🟢",
    tagline: "El Organizador",
    desc: "Sos metódico, confiable y orientado al proceso. Tenés una capacidad excepcional para organizar, planificar y ejecutar con precisión. Los demás confían en vos porque siempre cumplís lo que prometés.",
    traits: ["Metódico", "Confiable", "Detallista", "Organizado", "Disciplinado", "Consistente", "Planificador"],
    roles: ["Gerente de calidad", "Jefe de mantenimiento", "Auditor", "Administrador", "Coordinador de operaciones"],
    cls: "bl"
  },
  br: {
    name: "Basal Derecho",
    emoji: "🟠",
    tagline: "El Comunicador",
    desc: "Sos empático, comunicativo y orientado a las personas. Tenés una habilidad natural para conectar con otros, generar confianza y construir equipos cohesionados. Sos el corazón humano de cualquier organización.",
    traits: ["Empático", "Comunicativo", "Colaborativo", "Intuitivo", "Motivador", "Inclusivo", "Orientado al equipo"],
    roles: ["Gerente de RRHH", "Director de hospitalidad", "Facilitador", "Coach", "Gerente de servicio al cliente"],
    cls: "br"
  }
};

let current = 0;
let answers = new Array(questions.length).fill(null);

function startQuiz() {
  document.getElementById('intro').style.display = 'none';
  document.getElementById('quiz').style.display = 'block';
  renderQ();
}

function renderQ() {
  const q = questions[current];
  document.getElementById('qCounter').textContent = `Pregunta ${current + 1} de ${questions.length}`;
  document.getElementById('qText').textContent = q.text;

  const letters = ['A', 'B', 'C', 'D'];
  const opts = document.getElementById('options');
  opts.innerHTML = '';

  // Shuffle options
  const shuffled = [...q.opts].map((o, i) => ({ ...o, orig: i }));

  shuffled.forEach((opt, i) => {
    const btn = document.createElement('button');
    btn.className = 'opt-btn' + (answers[current] === opt.type ? ' selected' : '');
    btn.innerHTML = `<span class="opt-letter">${letters[i]}</span>${opt.text}`;
    btn.onclick = () => selectAnswer(opt.type);
    opts.appendChild(btn);
  });

  document.getElementById('btnPrev').style.visibility = current === 0 ? 'hidden' : 'visible';
  document.getElementById('btnNext').disabled = answers[current] === null;
  document.getElementById('btnNext').textContent = current === questions.length - 1 ? 'Ver mi perfil ✓' : 'Siguiente →';

  const pct = (current / questions.length) * 100;
  document.getElementById('progressFill').style.width = pct + '%';
}

function selectAnswer(type) {
  answers[current] = type;
  document.querySelectorAll('.opt-btn').forEach(b => b.classList.remove('selected'));
  document.querySelectorAll('.opt-btn').forEach(b => {
    if (b.textContent.trim().includes(questions[current].opts.find(o => o.type === type)?.text?.substring(0, 10))) {
      b.classList.add('selected');
    }
  });
  // Re-render to show selection properly
  renderQ();
  document.getElementById('btnNext').disabled = false;
}

function nextQ() {
  if (answers[current] === null) return;
  if (current === questions.length - 1) {
    showResults();
    return;
  }
  current++;
  renderQ();
}

function prevQ() {
  if (current > 0) { current--; renderQ(); }
}

function showResults() {
  document.getElementById('quiz').style.display = 'none';
  document.getElementById('results').style.display = 'block';
  document.getElementById('progressFill').style.width = '100%';

  const scores = { fl: 0, fr: 0, bl: 0, br: 0 };
  answers.forEach(a => { if (a) scores[a]++; });

  const total = questions.length;
  const winner = Object.entries(scores).sort((a, b) => b[1] - a[1])[0][0];
  const p = profiles[winner];

  // Winner card
  const wc = document.getElementById('winnerCard');
  wc.innerHTML = `
    <div class="winner-card ${p.cls}">
      <h3>${p.emoji} ${p.name}</h3>
      <div class="tagline">"${p.tagline}"</div>
      <p>${p.desc}</p>
    </div>
  `;

  // Score bars
  const sg = document.getElementById('scoreGrid');
  const labels = { fl: '🔵 Frontal Izquierdo', fr: '🟣 Frontal Derecho', bl: '🟢 Basal Izquierdo', br: '🟠 Basal Derecho' };
  sg.innerHTML = Object.entries(scores).sort((a,b) => b[1]-a[1]).map(([k, v]) => `
    <div class="score-item">
      <span class="score-label ${k}">${labels[k]}</span>
      <div class="score-bar-bg"><div class="score-bar ${k}" style="width:${Math.round(v/total*100)}%"></div></div>
      <span class="score-val">${v} respuestas · ${Math.round(v/total*100)}%</span>
    </div>
  `).join('');

  // Traits
  const tg = document.getElementById('traitsGrid');
  tg.innerHTML = p.traits.map(t => `<span class="trait-chip ${p.cls}">${t}</span>`).join('');

  // Roles
  document.getElementById('rolesSection').innerHTML = `
    <h4>💼 Roles donde este perfil se destaca</h4>
    <ul>${p.roles.map(r => `<li>${r}</li>`).join('')}</ul>
  `;

  window.scrollTo({ top: 0, behavior: 'smooth' });
}

function restart() {
  current = 0;
  answers = new Array(questions.length).fill(null);
  document.getElementById('results').style.display = 'none';
  document.getElementById('intro').style.display = 'block';
  document.getElementById('progressFill').style.width = '0%';
  window.scrollTo({ top: 0, behavior: 'smooth' });
}
</script>
</body>
</html>
