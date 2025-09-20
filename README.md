<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Escucha Joven — Habla anónimamente</title>
  <style>
    /* Reset y base */
    :root{
      --bg:#f7fbfb;
      --card:#ffffff;
      --accent:#146b6b; /* color principal (cambia aquí) */
      --accent-2:#2a9d8f;
      --muted:#6b6b6b;
      --radius:14px;
      --maxw:980px;
      --gap:22px;
    }
    *{box-sizing:border-box}
    body{
      margin:0; font-family:Inter, Roboto, "Helvetica Neue", Arial, sans-serif;
      background:var(--bg); color:#0b0b0b; -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.45;
    }
    .wrap{max-width:var(--maxw); margin:36px auto; padding:28px;}
    header.hero{
      background:linear-gradient(180deg, rgba(20,107,107,0.08), rgba(42,157,143,0.03));
      border-radius:var(--radius); padding:36px;
      display:flex; gap:var(--gap); align-items:center;
    }
    .hero-left{flex:1}
    .logo{
      display:inline-flex; align-items:center; gap:12px; margin-bottom:8px;
    }
    .logo .dot{width:42px;height:42px;background:var(--accent);border-radius:10px;display:inline-block}
    h1{margin:6px 0 10px;font-size:28px}
    p.lead{margin:0;color:var(--muted)}
    .cta-row{margin-top:18px;display:flex;gap:12px;flex-wrap:wrap}
    .btn{
      background:var(--accent); color:white; border:none; padding:12px 18px; border-radius:10px;
      font-weight:600; cursor:pointer; text-decoration:none; display:inline-flex; align-items:center; gap:10px;
    }
    .btn.ghost{background:transparent; border:1px solid rgba(10,10,10,0.06); color:var(--accent); font-weight:600;}
    /* card */
    .card{background:var(--card); border-radius:12px; padding:18px; box-shadow:0 6px 18px rgba(12,25,25,0.04)}
    .grid{display:grid; grid-template-columns:1fr 360px; gap:18px; align-items:start; margin-top:18px}
    /* info section */
    .how{display:grid; gap:12px}
    .how .step{display:flex; gap:12px; align-items:flex-start}
    .step .num{width:46px;height:46px;border-radius:10px;background:var(--accent-2); color:white; display:flex;align-items:center;justify-content:center;font-weight:700}
    .resources{display:flex;flex-direction:column;gap:12px}
    .resource-item{display:flex;gap:12px;align-items:center}
    .resource-item .icon{width:48px;height:48;border-radius:10px;background:linear-gradient(135deg,var(--accent),var(--accent-2));display:flex;align-items:center;justify-content:center;color:white;font-weight:700}
    /* chat panel */
    .chat-panel{position:relative;height:420px;border-radius:12px;overflow:hidden}
    .chat-frame{
      width:100%; height:100%; border:0;
      display:block;
    }
    footer{margin-top:18px; text-align:center; color:var(--muted); font-size:13px}
    /* responsive */
    @media (max-width:900px){
      .grid{grid-template-columns:1fr; margin-top:12px}
      .chat-panel{height:360px}
      header.hero{flex-direction:column; align-items:flex-start}
    }
    /* small helpers */
    .muted{color:var(--muted); font-size:14px}
    .pill{display:inline-block;padding:6px 10px;border-radius:999px;background:rgba(20,107,107,0.08);color:var(--accent);font-weight:600}
  </style>
</head>
<body>
  <div class="wrap">
    <!-- HERO -->
    <header class="hero card">
      <div class="hero-left">
        <div class="logo">
          <span class="dot" aria-hidden="true"></span>
          <div>
            <div style="font-weight:700">Escucha Joven</div>
            <div style="font-size:13px;color:var(--muted)">Espacio anónimo y seguro para hablar</div>
          </div>
        </div>
        <h1>Habla ahora. Nadie te juzga. Nadie necesita tus datos.</h1>
        <p class="lead">Si te sientes solo, abrumado o confundido, aquí puedes desahogarte de forma 100% anónima. Nuestro asistente te escucha y te ofrece recursos y medidas concretas.</p>

        <div class="cta-row">
          <!-- BOTÓN PRINCIPAL: reemplaza '#open-chat' por el ID, o conecta al script del chatbot -->
          <a class="btn" href="#open-chat" id="openChatBtn">🗨️ Iniciar chat anónimo</a>
          <a class="btn ghost" href="#recursos">📚 Recursos y ayuda</a>
        </div>

        <div style="margin-top:12px" class="muted">
          Gratis · Anónimo · Disponible 24/7
        </div>
      </div>

      <!-- PANEL DERECHO: resumen + micro FAQ -->
      <aside style="width:320px">
        <div class="card">
          <div style="font-weight:700; margin-bottom:8px">¿Por qué confiar?</div>
          <div class="muted" style="font-size:14px">
            No pedimos correo, nombre ni teléfono. Todas las conversaciones pueden configurarse para no guardarse. En caso de riesgo, verás enlaces directos a líneas de ayuda.
          </div>

          <hr style="margin:14px 0;border:none;border-top:1px solid #f0f0f0" />

          <div style="display:flex;gap:8px;align-items:center;justify-content:space-between">
            <div>
              <div style="font-weight:700">Disponible ahora</div>
              <div class="muted" style="font-size:13px">Chat automático + opción a voluntario</div>
            </div>
            <div class="pill">Anonimato</div>
          </div>
        </div>
      </aside>
    </header>

    <!-- GRID principal -->
    <div class="grid">
      <!-- COLUMNA PRINCIPAL -->
      <main>
        <section class="card how" id="como-funciona" style="margin-bottom:18px">
          <h2 style="margin:0 0 6px">Cómo funciona</h2>
          <div class="muted" style="margin-bottom:8px">Todo pensado para que sea rápido y sencillo.</div>

          <div class="step">
            <div class="num">1</div>
            <div>
              <div style="font-weight:700">Entra y escribe</div>
              <div class="muted">No necesitas registro ni datos personales. Empieza a escribir lo que te preocupa.</div>
            </div>
          </div>

          <div class="step">
            <div class="num">2</div>
            <div>
              <div style="font-weight:700">Recibe escucha y recursos</div>
              <div class="muted">Nuestro asistente te escucha, hace preguntas y sugiere pasos prácticos.</div>
            </div>
          </div>

          <div class="step">
            <div class="num">3</div>
            <div>
              <div style="font-weight:700">Si hace falta, te derivamos</div>
              <div class="muted">Si detectamos riesgo, mostramos números de emergencia y opciones con profesionales.</div>
            </div>
          </div>
        </section>

        <section class="card" id="recursos">
          <h3 style="margin-top:0">Recursos de emergencia</h3>
          <div class="resources">
            <div class="resource-item">
              <div class="icon">☎️</div>
              <div>
                <div style="font-weight:700">Línea local de emergencia</div>
                <div class="muted">Si estás en peligro, llama a los servicios de emergencia de tu país.</div>
              </div>
            </div>

            <div class="resource-item">
              <div class="icon">🆘</div>
              <div>
                <div style="font-weight:700">Teléfono de la Esperanza (España)</div>
                <div class="muted">717 003 717 — Si estás en España, llama si estás en crisis.</div>
              </div>
            </div>

            <div class="resource-item">
              <div class="icon">🔗</div>
              <div>
                <div style="font-weight:700">Busca ayuda en tu país</div>
                <div class="muted">Consulta recursos locales y líneas de apoyo profesional.</div>
              </div>
            </div>
          </div>
        </section>

        <section class="card" style="margin-top:18px">
          <h3 style="margin-top:0">Aviso importante</h3>
          <div class="muted">
            Este servicio ofrece apoyo emocional básico y escucha entre pares; <strong>no</strong> sustituye la atención médica o psicológica profesional. Si existe riesgo inminente de daño, contacta a los servicios de emergencia.
          </div>
        </section>
      </main>

      <!-- PANEL CHAT (COL 2) -->
      <aside>
        <div class="card chat-panel" aria-hidden="false">
          <!-- Aquí se carga el chatbot en un iframe o integrando el script del proveedor -->
          <!-- Reemplaza src="about:blank" por la URL de tu Landbot/Tidio/otro en embed -->
          <iframe id="chatFrame" class="chat-frame" src="about:blank" title="Chat anónimo - Escucha Joven"></iframe>
        </div>

        <div style="margin-top:12px" class="card">
          <div style="font-weight:700">¿No quieres usar el chat ahora?</div>
          <div class="muted" style="margin-top:8px">Puedes usar también nuestro bot en Telegram o leer recursos hasta sentirte listo.</div>
          <div style="margin-top:12px;display:flex;gap:8px">
            <a class="btn ghost" href="#" id="telegramBtn">Telegram</a>
            <a class="btn ghost" href="#" id="openResourcesBtn">Ver recursos</a>
          </div>
        </div>
      </aside>
    </div>

    <footer>
      © <span id="year"></span> Escucha Joven — Plataforma de apoyo anónimo · <a href="#aviso" style="color:var(--accent)">Aviso legal</a>
    </footer>
  </div>

  <script>
    // Rellenar año
    document.getElementById('year').textContent = new Date().getFullYear();

    // ---------- CONFIGURACIÓN: Cambia aquí los enlaces del chatbot ----------
    // 1) Si usas Landbot: pega la URL de embed (ej: "https://landbot.io/..." o el iframe que te da Landbot)
    // 2) Si usas Tidio: puedes cargar el script de Tidio (ver instrucciones más abajo) - para Wix pega el script global en Configuración de sitio
    // 3) Si usas Telegram: pon tu enlace 'https://t.me/TU_BOT'
    //
    // Reemplaza las variables siguientes por tus enlaces/IDs:
    const CHAT_IFRAME_SRC = "about:blank"; // <-- pega aquí la URL del iframe del bot (o el HTML hosteado del chat)
    const TELEGRAM_LINK = "https://t.me/tu_bot_aqui"; // <-- reemplaza con tu bot de Telegram
    const LANDBOT_EMBED_URL = ""; // si tienes una URL de Landbot (opcional)

    // Pegar chat en iframe
    const chatFrame = document.getElementById('chatFrame');
    if (LANDBOT_EMBED_URL && LANDBOT_EMBED_URL.trim() !== "") {
      chatFrame.src = LANDBOT_EMBED_URL;
    } else if (CHAT_IFRAME_SRC && CHAT_IFRAME_SRC !== "about:blank") {
      chatFrame.src = CHAT_IFRAME_SRC;
    } else {
      // Contenido por defecto (modo demostración)
      chatFrame.srcdoc = `
        <div style="font-family:Inter, Roboto, Arial; padding:18px; background:#fff; height:100%;">
          <h3 style="margin-top:0;color:${getComputedStyle(document.documentElement).getPropertyValue('--accent').trim()}">Chat de demostración</h3>
          <p style="color:#444">Aquí irá tu chatbot real.</p>
          <p style="color:#666;font-size:13px">Sustituye el iframe por la URL de Landbot/Tidio o por tu widget.</p>
        </div>
      `;
    }

    // Botones de navegación
    document.getElementById('openChatBtn').addEventListener('click', function(e){
      e.preventDefault();
      // desplaza hacia el iframe
      document.getElementById('chatFrame').scrollIntoView({behavior:'smooth', block:'center'});
    });
    document.getElementById('telegramBtn').addEventListener('click', function(e){
      e.preventDefault();
      window.open(TELEGRAM_LINK, '_blank');
    });
    document.getElementById('openResourcesBtn').addEventListener('click', function(e){
      e.preventDefault();
      document.getElementById('recursos').scrollIntoView({behavior:'smooth'});
    });
  </script>
</body>
</html>
