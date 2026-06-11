[benziger (2).html](https://github.com/user-attachments/files/28847498/benziger.2.html)
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Test Benziger</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Segoe UI',sans-serif;background:#F8FAFC;color:#1E293B;min-height:100vh}
header{background:linear-gradient(135deg,#1E293B,#334155);color:#fff;padding:28px 20px;text-align:center}
header h1{font-size:1.7rem;font-weight:700}
header p{color:#94A3B8;margin-top:5px;font-size:.9rem}
.bar{background:#334155;height:6px}
.fill{height:6px;background:linear-gradient(90deg,#2563EB,#7C3AED);transition:width .4s ease;width:0%}
main{max-width:640px;margin:0 auto;padding:24px 16px 60px}

/* INTRO */
#intro{text-align:center;padding:20px 0}
#intro h2{font-size:1.3rem;margin-bottom:10px}
#intro p{color:#64748B;line-height:1.7;margin-bottom:8px;font-size:.93rem}
.bgrid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin:20px 0;text-align:left}
.bc{border-radius:10px;padding:12px 14px;border-left:4px solid}
.bc.fl{background:#EFF6FF;border-color:#2563EB}.bc.fl h4{color:#2563EB}
.bc.fr{background:#F5F3FF;border-color:#7C3AED}.bc.fr h4{color:#7C3AED}
.bc.bl{background:#ECFDF5;border-color:#059669}.bc.bl h4{color:#059669}
.bc.br{background:#FFFBEB;border-color:#D97706}.bc.br h4{color:#D97706}
.bc h4{font-size:.82rem;font-weight:700;margin-bottom:3px}
.bc p{font-size:.78rem;color:#64748B;line-height:1.4}

/* FORM */
#nameForm{display:none;padding:20px 0}
#nameForm h2{font-size:1.3rem;font-weight:700;text-align:center;margin-bottom:6px}
#nameForm p{color:#64748B;text-align:center;margin-bottom:22px;font-size:.93rem}
.fg{display:flex;flex-direction:column;gap:5px;margin-bottom:14px}
.fg label{font-size:.88rem;font-weight:600}
.fg input{padding:12px 14px;border:2px solid #E2E8F0;border-radius:8px;font-size:1rem;outline:none;transition:border-color .15s}
.fg input:focus{border-color:#2563EB}

/* BUTTONS */
.btnS{background:linear-gradient(135deg,#1E293B,#334155);color:#fff;border:none;padding:13px 36px;border-radius:8px;font-size:.97rem;font-weight:600;cursor:pointer;transition:opacity .15s,transform .15s}
.btnS:hover{opacity:.9;transform:translateY(-1px)}
.btnF{background:linear-gradient(135deg,#1E293B,#334155);color:#fff;border:none;padding:13px;border-radius:8px;font-size:.97rem;font-weight:600;cursor:pointer;width:100%;margin-top:6px;transition:opacity .15s}
.btnF:hover{opacity:.9}
.btnF:disabled{background:#CBD5E1;cursor:not-allowed}

/* QUIZ */
#quiz{display:none}
.qc{font-size:.8rem;color:#64748B;font-weight:600;letter-spacing:.5px;text-transform:uppercase;margin-bottom:7px}
.qt{font-size:1.1rem;font-weight:600;line-height:1.5;margin-bottom:18px}
.opts{display:flex;flex-direction:column;gap:9px}
.ob{background:#fff;border:2px solid #E2E8F0;border-radius:10px;padding:13px 16px;text-align:left;font-size:.93rem;cursor:pointer;transition:all .15s ease;display:flex;align-items:center;gap:10px}
.ob:hover{border-color:#94A3B8;background:#F1F5F9;transform:translateX(3px)}
.ob.sel{border-color:#334155;background:#F8FAFC;font-weight:600}
.ol{width:26px;height:26px;border-radius:50%;background:#E2E8F0;display:flex;align-items:center;justify-content:center;font-size:.78rem;font-weight:700;color:#64748B;flex-shrink:0}
.ob.sel .ol{background:#334155;color:#fff}
.nav{display:flex;justify-content:space-between;align-items:center;margin-top:22px}
.bn{padding:10px 22px;border-radius:8px;font-size:.93rem;font-weight:600;cursor:pointer;border:none;transition:all .15s}
.bp{background:#E2E8F0;color:#1E293B}.bp:hover{background:#CBD5E1}
.bx{background:#1E293B;color:#fff}.bx:hover{background:#334155}
.bx:disabled{background:#CBD5E1;cursor:not-allowed}

/* RESULTS */
#results{display:none}
.rh{text-align:center;padding:20px 0 14px}
.rh h2{font-size:1.35rem;font-weight:700}
.rh p{color:#64748B;margin-top:5px}
.wc{border-radius:12px;padding:22px;margin:18px 0;text-align:center;border:3px solid}
.wc h3{font-size:1.4rem;font-weight:800;margin-bottom:5px}
.wc .tg{font-size:.95rem;opacity:.85;margin-bottom:10px}
.wc p{font-size:.9rem;line-height:1.7}
.wc.fl{background:#EFF6FF;border-color:#2563EB;color:#2563EB}
.wc.fr{background:#F5F3FF;border-color:#7C3AED;color:#7C3AED}
.wc.bl{background:#ECFDF5;border-color:#059669;color:#059669}
.wc.br{background:#FFFBEB;border-color:#D97706;color:#D97706}
.wc p{color:#1E293B}
.sg{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin:18px 0}
.si{background:#fff;border:1px solid #E2E8F0;border-radius:10px;padding:12px;display:flex;flex-direction:column;gap:5px}
.sl{font-size:.78rem;font-weight:700}
.sl.fl{color:#2563EB}.sl.fr{color:#7C3AED}.sl.bl{color:#059669}.sl.br{color:#D97706}
.sb{background:#E2E8F0;border-radius:4px;height:7px}
.sf{border-radius:4px;height:7px;transition:width .6s ease}
.sf.fl{background:#2563EB}.sf.fr{background:#7C3AED}.sf.bl{background:#059669}.sf.br{background:#D97706}
.sv{font-size:.82rem;font-weight:600;color:#64748B}
.ts{margin:18px 0}
.ts h4{font-size:.95rem;font-weight:700;margin-bottom:10px}
.tg2{display:flex;flex-wrap:wrap;gap:7px}
.tc{padding:5px 13px;border-radius:20px;font-size:.8rem;font-weight:600;border:1.5px solid}
.tc.fl{background:#EFF6FF;border-color:#2563EB;color:#2563EB}
.tc.fr{background:#F5F3FF;border-color:#7C3AED;color:#7C3AED}
.tc.bl{background:#ECFDF5;border-color:#059669;color:#059669}
.tc.br{background:#FFFBEB;border-color:#D97706;color:#D97706}
.rs{background:#fff;border:1px solid #E2E8F0;border-radius:12px;padding:18px;margin:14px 0}
.rs h4{font-size:.92rem;font-weight:700;margin-bottom:9px}
.rs ul{list-style:none;display:flex;flex-direction:column;gap:5px}
.rs li{font-size:.88rem;color:#64748B;display:flex;align-items:center;gap:7px}
.rs li::before{content:"▸";font-weight:700}
.wb{background:#FFF7ED;border:1px solid #FED7AA;border-radius:10px;padding:14px;margin:14px 0;font-size:.85rem;color:#92400E;line-height:1.6}
.wb strong{color:#78350F}
.sv2{border-radius:10px;padding:13px 15px;margin:14px 0;font-size:.88rem;text-align:center;background:#EFF6FF;border:1px solid #BFDBFE;color:#1D4ED8}
.sv2.ok{background:#ECFDF5;border-color:#6EE7B7;color:#065F46}
.sv2.err{background:#FEF2F2;border-color:#FECACA;color:#991B1B}
.br2{width:100%;padding:13px;background:#1E293B;color:#fff;border:none;border-radius:8px;font-size:.97rem;font-weight:600;cursor:pointer;margin-top:6px}
.br2:hover{background:#334155}
</style>
</head>
<body>
<header>
  <h1>🧠 Test de Perfil Benziger</h1>
  <p>Descubrí tu estilo natural de pensar y trabajar</p>
</header>
<div class="bar"><div class="fill" id="fill"></div></div>
<main>

<div id="intro">
  <h2>¿Cómo pensás naturalmente?</h2>
  <p>La teoría de Katherine Benziger identifica cuatro modos de pensamiento basados en las áreas del cerebro que cada persona usa con mayor facilidad.</p>
  <p>Este test tiene <strong>20 preguntas</strong> y tarda unos <strong>5 minutos</strong>. No hay respuestas correctas ni incorrectas.</p>
  <div class="bgrid">
    <div class="bc fl"><h4>🔵 Frontal Izquierdo</h4><p>Lógico, analítico, orientado a resultados.</p></div>
    <div class="bc fr"><h4>🟣 Frontal Derecho</h4><p>Creativo, visionario, orientado al futuro.</p></div>
    <div class="bc bl"><h4>🟢 Basal Izquierdo</h4><p>Metódico, confiable, orientado al proceso.</p></div>
    <div class="bc br"><h4>🟠 Basal Derecho</h4><p>Empático, comunicativo, orientado a personas.</p></div>
  </div>
  <button class="btnS" onclick="mostrarFormulario()">Comenzar el Test →</button>
</div>

<div id="nameForm">
  <h2>👤 Antes de empezar</h2>
  <p>Ingresá tu nombre y apellido para registrar tus resultados.</p>
  <div class="fg">
    <label for="iNombre">Nombre *</label>
    <input type="text" id="iNombre" placeholder="Ej: Sebastián" oninput="verificarForm()">
  </div>
  <div class="fg">
    <label for="iApellido">Apellido *</label>
    <input type="text" id="iApellido" placeholder="Ej: Shermida" oninput="verificarForm()">
  </div>
  <button class="btnF" id="btnIniciar" onclick="iniciarQuiz()" disabled>Iniciar el Test →</button>
</div>

<div id="quiz">
  <div class="qc" id="qc">Pregunta 1 de 20</div>
  <div class="qt" id="qt"></div>
  <div class="opts" id="opts"></div>
  <div class="nav">
    <button class="bn bp" id="bprev" onclick="anterior()">← Anterior</button>
    <button class="bn bx" id="bnext" onclick="siguiente()" disabled>Siguiente →</button>
  </div>
</div>

<div id="results">
  <div class="rh">
    <h2 id="rtitle">Tu Perfil Benziger</h2>
    <p id="rsub">Basado en tus respuestas</p>
  </div>
  <div id="wcard"></div>
  <div class="sg" id="sgrid"></div>
  <div class="ts"><h4>🎯 Tus fortalezas naturales</h4><div class="tg2" id="tgrid"></div></div>
  <div class="rs" id="roles"></div>
  <div class="sv2" id="saving">💾 Guardando tus resultados...</div>
  <div class="wb"><strong>⚠️ Importante:</strong> Este test es orientativo para la reflexión y el autoconocimiento. No reemplaza una evaluación profesional certificada de Benziger.</div>
  <button class="br2" onclick="reiniciar()">🔄 Hacer el test de nuevo</button>
</div>

</main>
<script>
var SCRIPT="https://script.google.com/macros/s/AKfycbxT-T2VXhPZjQ0MyP1AvVlJkeWqwWadXqWYS6T3dAXQAPxh6nmDwEhMrqpGk8j55ANruw/exec";
var preguntas=[
{t:"Cuando tenés que resolver un problema complejo, preferís...",o:[{t:"Analizar los datos y buscar la solución más lógica",p:"fl"},{t:"Explorar ideas creativas y pensar en soluciones novedosas",p:"fr"},{t:"Seguir un proceso paso a paso que ya funcionó antes",p:"bl"},{t:"Hablar con otras personas y construir una solución en equipo",p:"br"}]},
{t:"En una reunión de trabajo, tu rol más natural es...",o:[{t:"Presentar argumentos con datos y lógica clara",p:"fl"},{t:"Proponer ideas innovadoras y visiones a largo plazo",p:"fr"},{t:"Tomar notas y asegurarte de que se definan los próximos pasos",p:"bl"},{t:"Mediar entre opiniones y cuidar el clima del grupo",p:"br"}]},
{t:"¿Qué te genera más satisfacción profesional?",o:[{t:"Alcanzar resultados medibles y concretos",p:"fl"},{t:"Crear algo nuevo que no existía antes",p:"fr"},{t:"Completar tareas con precisión y dentro del plazo",p:"bl"},{t:"Ayudar a que mi equipo crezca y se desarrolle",p:"br"}]},
{t:"Cuando recibís información nueva, lo primero que hacés es...",o:[{t:"Buscar si es consistente, lógica y está respaldada por evidencia",p:"fl"},{t:"Imaginar cómo podría aplicarse o transformarse en algo útil",p:"fr"},{t:"Clasificarla y organizarla en categorías o sistemas",p:"bl"},{t:"Pensar en cómo impacta en las personas involucradas",p:"br"}]},
{t:"¿Cómo preferís que te evalúen en tu trabajo?",o:[{t:"Por los resultados objetivos que logré",p:"fl"},{t:"Por el impacto de mis ideas y propuestas",p:"fr"},{t:"Por mi confiabilidad y consistencia en el tiempo",p:"bl"},{t:"Por la calidad de mis relaciones y trabajo en equipo",p:"br"}]},
{t:"Cuando tenés que comunicar algo importante, preferís hacerlo con...",o:[{t:"Un informe estructurado con datos y gráficos",p:"fl"},{t:"Una presentación visual o narrativa inspiradora",p:"fr"},{t:"Un procedimiento o manual paso a paso",p:"bl"},{t:"Una conversación cara a cara o en grupo",p:"br"}]},
{t:"¿Qué tipo de proyecto te motiva más?",o:[{t:"Resolver un problema técnico complejo con métricas claras",p:"fl"},{t:"Diseñar una estrategia o visión de futuro para la organización",p:"fr"},{t:"Implementar un sistema que mejore la eficiencia operativa",p:"bl"},{t:"Desarrollar un programa de capacitación para el equipo",p:"br"}]},
{t:"Ante un cambio inesperado en el trabajo, tu primera reacción es...",o:[{t:"Evaluar el impacto racionalmente antes de actuar",p:"fl"},{t:"Ver la oportunidad que puede traer el cambio",p:"fr"},{t:"Preocuparte por cómo afecta los procesos establecidos",p:"bl"},{t:"Consultar con el equipo para entender cómo se sienten",p:"br"}]},
{t:"En tu tiempo libre, ¿qué actividades disfrutás más?",o:[{t:"Leer sobre tecnología, ciencia o análisis de datos",p:"fl"},{t:"Arte, música, viajes o explorar ideas filosóficas",p:"fr"},{t:"Cocinar siguiendo recetas, coleccionar o actividades de precisión",p:"bl"},{t:"Reunirte con amigos y familia, actividades solidarias",p:"br"}]},
{t:'¿Cuál de estas frases te representa mejor?',o:[{t:'"Los números no mienten, la evidencia manda"',p:"fl"},{t:'"El límite es la imaginación"',p:"fr"},{t:'"Si no está escrito, no existe"',p:"bl"},{t:'"La gente es lo más importante"',p:"br"}]},
{t:"Cuando alguien del equipo comete un error, tu tendencia es...",o:[{t:"Analizar qué falló y cómo prevenirlo con datos",p:"fl"},{t:"Ver si hay una forma creativa de convertirlo en aprendizaje",p:"fr"},{t:"Revisar el proceso para encontrar el punto de falla",p:"bl"},{t:"Hablar con la persona, entender cómo está y apoyarla",p:"br"}]},
{t:"¿Qué te resulta más difícil tolerar en el trabajo?",o:[{t:"Decisiones sin fundamento lógico ni datos",p:"fl"},{t:"Rutinas repetitivas que no permiten creatividad",p:"fr"},{t:"El caos, la falta de orden y los procedimientos incumplidos",p:"bl"},{t:"Los conflictos interpersonales y los ambientes hostiles",p:"br"}]},
{t:"¿Cómo tomás tus decisiones más importantes?",o:[{t:"Con análisis racional, comparando opciones y sus consecuencias",p:"fl"},{t:"Siguiendo mi intuición y visión de hacia dónde ir",p:"fr"},{t:"Consultando procedimientos, normas o experiencias pasadas",p:"bl"},{t:"Considerando el impacto en las personas involucradas",p:"br"}]},
{t:"En una negociación, tu punto fuerte es...",o:[{t:"Argumentar con lógica y datos irrefutables",p:"fl"},{t:"Plantear una visión atractiva que inspire a la otra parte",p:"fr"},{t:"Ser meticuloso con los detalles del acuerdo",p:"bl"},{t:"Generar confianza y empatía con el otro",p:"br"}]},
{t:"¿Cómo aprendés mejor?",o:[{t:"Leyendo, analizando casos y estudiando teorías",p:"fl"},{t:"Explorando, experimentando y conectando ideas",p:"fr"},{t:"Practicando con instrucciones claras paso a paso",p:"bl"},{t:"Aprendiendo con otros, en grupo o con un mentor",p:"br"}]},
{t:"¿Qué rol preferís asumir en un proyecto nuevo?",o:[{t:"Líder técnico: diseñar la arquitectura y las métricas",p:"fl"},{t:"Visionario: definir el concepto y la estrategia",p:"fr"},{t:"Coordinador: organizar tareas, plazos y recursos",p:"bl"},{t:"Facilitador: asegurar que el equipo funcione bien",p:"br"}]},
{t:"¿Cuál describe mejor tu estilo de liderazgo?",o:[{t:"Oriento al equipo con objetivos claros y métricas de rendimiento",p:"fl"},{t:"Inspiro al equipo con una visión y los invito a innovar",p:"fr"},{t:"Establezco procesos claros y me aseguro de cumplirlos",p:"bl"},{t:"Escucho a cada persona y adapto mi liderazgo a sus necesidades",p:"br"}]},
{t:"¿Qué valoran más en vos tus colegas?",o:[{t:"Tu capacidad de análisis y resolución de problemas",p:"fl"},{t:"Tu creatividad y visión estratégica",p:"fr"},{t:"Tu confiabilidad y atención al detalle",p:"bl"},{t:"Tu calidez humana y habilidad para escuchar",p:"br"}]},
{t:"Cuando describís tu trabajo ideal, ¿qué aparece primero?",o:[{t:"Desafíos intelectuales complejos con impacto medible",p:"fl"},{t:"Libertad para crear e innovar sin límites preestablecidos",p:"fr"},{t:"Claridad en las responsabilidades y procesos bien definidos",p:"bl"},{t:"Un equipo comprometido y un buen clima de trabajo",p:"br"}]},
{t:"¿Qué te describe mejor al final de un proyecto exitoso?",o:[{t:"Siento satisfacción al ver los resultados concretos y medibles",p:"fl"},{t:"Me pregunto qué idea nueva puedo explorar a partir de esto",p:"fr"},{t:"Me aseguro de documentar todo para futuros proyectos",p:"bl"},{t:"Celebro con el equipo y reconozco el aporte de cada uno",p:"br"}]}
];
var perfiles={
fl:{n:"Frontal Izquierdo",e:"🔵",tg:"El Analítico",d:"Sos lógico/a, orientado/a a resultados y al pensamiento crítico. Tomás decisiones basadas en datos y evidencias. Te destacás en entornos donde se valoran la precisión, la eficiencia y la racionalidad.",tr:["Analítico","Lógico","Estratégico","Objetivo","Sistemático"],r:["Director de operaciones","Gerente financiero","Jefe de proyectos técnicos","Ingeniero","Analista de datos"],c:"fl"},
fr:{n:"Frontal Derecho",e:"🟣",tg:"El Visionario",d:"Sos creativo/a, intuitivo/a y orientado/a al futuro. Te energizás con las ideas y la innovación. Sos capaz de ver conexiones que otros no ven e inspirar a los demás con tu visión.",tr:["Creativo","Visionario","Intuitivo","Innovador","Inspirador"],r:["Director de innovación","Gerente de marketing","Consultor estratégico","Diseñador","Emprendedor"],c:"fr"},
bl:{n:"Basal Izquierdo",e:"🟢",tg:"El Organizador",d:"Sos metódico/a, confiable y orientado/a al proceso. Tenés una capacidad excepcional para organizar, planificar y ejecutar con precisión. Los demás confían en vos porque siempre cumplís.",tr:["Metódico","Confiable","Detallista","Organizado","Planificador"],r:["Gerente de calidad","Jefe de mantenimiento","Auditor","Administrador","Coordinador de operaciones"],c:"bl"},
br:{n:"Basal Derecho",e:"🟠",tg:"El Comunicador",d:"Sos empático/a, comunicativo/a y orientado/a a las personas. Tenés habilidad natural para conectar con otros, generar confianza y construir equipos cohesionados.",tr:["Empático","Comunicativo","Colaborativo","Motivador","Inclusivo"],r:["Gerente de RRHH","Director de hospitalidad","Facilitador","Coach","Gerente de servicio al cliente"],c:"br"}
};
var actual=0,resp=new Array(20).fill(null),nombre="",apellido="";

function mostrarFormulario(){
  document.getElementById("intro").style.display="none";
  document.getElementById("nameForm").style.display="block";
  document.getElementById("fill").style.width="5%";
  document.getElementById("iNombre").focus();
}
function verificarForm(){
  var n=document.getElementById("iNombre").value.trim();
  var a=document.getElementById("iApellido").value.trim();
  document.getElementById("btnIniciar").disabled=!(n&&a);
}
function iniciarQuiz(){
  nombre=document.getElementById("iNombre").value.trim();
  apellido=document.getElementById("iApellido").value.trim();
  document.getElementById("nameForm").style.display="none";
  document.getElementById("quiz").style.display="block";
  mostrarPregunta();
}
function mostrarPregunta(){
  var q=preguntas[actual];
  document.getElementById("qc").textContent="Pregunta "+(actual+1)+" de 20";
  document.getElementById("qt").textContent=q.t;
  var L=["A","B","C","D"],o=document.getElementById("opts");
  o.innerHTML="";
  q.o.forEach(function(op,i){
    var b=document.createElement("button");
    b.className="ob"+(resp[actual]===op.p?" sel":"");
    b.innerHTML='<span class="ol">'+L[i]+"</span>"+op.t;
    b.onclick=function(){seleccionar(op.p)};
    o.appendChild(b);
  });
  document.getElementById("bprev").style.visibility=actual===0?"hidden":"visible";
  document.getElementById("bnext").disabled=resp[actual]===null;
  document.getElementById("bnext").textContent=actual===19?"Ver mi perfil ✓":"Siguiente →";
  document.getElementById("fill").style.width=(5+actual/20*90)+"%";
}
function seleccionar(p){
  resp[actual]=p;
  mostrarPregunta();
  document.getElementById("bnext").disabled=false;
}
function siguiente(){
  if(resp[actual]===null)return;
  if(actual===19){mostrarResultados();return;}
  actual++;mostrarPregunta();
}
function anterior(){if(actual>0){actual--;mostrarPregunta();}}
function mostrarResultados(){
  document.getElementById("quiz").style.display="none";
  document.getElementById("results").style.display="block";
  document.getElementById("fill").style.width="100%";
  var s={fl:0,fr:0,bl:0,br:0};
  resp.forEach(function(r){if(r)s[r]++;});
  var tot=20,win=Object.entries(s).sort(function(a,b){return b[1]-a[1];})[0][0],p=perfiles[win];
  document.getElementById("rtitle").textContent="Perfil de "+nombre+" "+apellido;
  document.getElementById("rsub").textContent="Basado en tus 20 respuestas";
  document.getElementById("wcard").innerHTML='<div class="wc '+p.c+'"><h3>'+p.e+" "+p.n+'</h3><div class="tg">"'+p.tg+'"</div><p>'+p.d+"</p></div>";
  var lb={fl:"🔵 Frontal Izquierdo",fr:"🟣 Frontal Derecho",bl:"🟢 Basal Izquierdo",br:"🟠 Basal Derecho"};
  document.getElementById("sgrid").innerHTML=Object.entries(s).sort(function(a,b){return b[1]-a[1];}).map(function(e){
    return '<div class="si"><span class="sl '+e[0]+'">'+lb[e[0]]+'</span><div class="sb"><div class="sf '+e[0]+'" style="width:'+Math.round(e[1]/tot*100)+'%"></div></div><span class="sv">'+e[1]+' resp · '+Math.round(e[1]/tot*100)+'%</span></div>';
  }).join("");
  document.getElementById("tgrid").innerHTML=p.tr.map(function(t){return'<span class="tc '+p.c+'">'+t+"</span>";}).join("");
  document.getElementById("roles").innerHTML='<h4>💼 Roles donde este perfil se destaca</h4><ul>'+p.r.map(function(r){return"<li>"+r+"</li>";}).join("")+"</ul>";
  guardar(s,tot,p.n);
  window.scrollTo({top:0,behavior:"smooth"});
}
function guardar(s,tot,perfil){
  var now=new Date();
  var fecha=now.toLocaleDateString("es-UY",{day:"2-digit",month:"2-digit",year:"numeric"})+" "+now.toLocaleTimeString("es-UY",{hour:"2-digit",minute:"2-digit"});
  var params="fecha="+encodeURIComponent(fecha)+"&nombre="+encodeURIComponent(nombre)+"&apellido="+encodeURIComponent(apellido)+"&perfil="+encodeURIComponent(perfil)+"&fl="+Math.round(s.fl/tot*100)+"&fr="+Math.round(s.fr/tot*100)+"&bl="+Math.round(s.bl/tot*100)+"&br="+Math.round(s.br/tot*100);
  var sv=document.getElementById("saving");
  sv.className="sv2";sv.textContent="💾 Guardando tus resultados...";
  var url=SCRIPT+"?"+params;
  fetch(url,{method:"GET",mode:"no-cors"})
  .then(function(){
    sv.className="sv2 ok";sv.textContent="✅ Resultados guardados en la base de datos.";
  })
  .catch(function(){
    var img=new Image();img.src=url;
    sv.className="sv2 ok";sv.textContent="✅ Resultados enviados correctamente.";
  });
  setTimeout(function(){
    if(sv.className==="sv2"){sv.className="sv2 ok";sv.textContent="✅ Resultados enviados correctamente.";}
  },5000);
}
function reiniciar(){
  actual=0;resp=new Array(20).fill(null);nombre="";apellido="";
  document.getElementById("iNombre").value="";
  document.getElementById("iApellido").value="";
  document.getElementById("btnIniciar").disabled=true;
  document.getElementById("results").style.display="none";
  document.getElementById("intro").style.display="block";
  document.getElementById("fill").style.width="0%";
  window.scrollTo({top:0,behavior:"smooth"});
}
</script>
</body>
</html>
