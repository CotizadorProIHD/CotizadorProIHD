<!doctype html>
<html lang="es-MX">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Cotizador PRO v3 - Paquetes Globos</title>

  <meta name="theme-color" content="#111827" />

  <!-- ✅ PWA / iPhone -->
  <link rel="manifest" href="./manifest.webmanifest">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
  <meta name="apple-mobile-web-app-title" content="Cotizador">
  <link rel="apple-touch-icon" href="./icons/icon-192.png">

  <style>
    :root{
      --bg:#0b1220;
      --txt:#e5e7eb;
      --muted:#9ca3af;
      --brand:#ff4da6;
      --brand2:#7c3aed;
      --shadow: 0 10px 25px rgba(0,0,0,.25);
      --radius:16px;
      --line: rgba(255,255,255,.08);
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Arial;
      background: radial-gradient(1200px 600px at 10% 0%, rgba(255,77,166,.20), transparent 60%),
                  radial-gradient(900px 500px at 90% 10%, rgba(124,58,237,.18), transparent 60%),
                  linear-gradient(180deg, #050914, var(--bg));
      color:var(--txt);
    }
    header{
      position:sticky; top:0; z-index:10;
      backdrop-filter: blur(10px);
      background: rgba(5,9,20,.65);
      border-bottom:1px solid rgba(255,255,255,.06);
    }
    .wrap{max-width:1100px;margin:0 auto;padding:14px 16px}
    .top{display:flex; align-items:center; justify-content:space-between; gap:12px;}
    .brand{display:flex; gap:10px; align-items:center;}
    .logo{
      width:38px;height:38px;border-radius:12px;
      background: linear-gradient(135deg, var(--brand), var(--brand2));
      box-shadow: var(--shadow);
    }
    h1{font-size:16px;margin:0}
    .sub{font-size:12px;color:var(--muted);margin-top:2px}

    nav{display:flex; gap:8px; margin-top:12px; flex-wrap:wrap;}
    .tab{
      border:1px solid rgba(255,255,255,.10);
      background: rgba(17,24,39,.55);
      color:var(--txt);
      padding:10px 12px;
      border-radius: 999px;
      cursor:pointer;
      font-weight:700;
      font-size:13px;
    }
    .tab.active{
      background: linear-gradient(135deg, rgba(255,77,166,.25), rgba(124,58,237,.20));
      border-color: rgba(255,255,255,.18);
    }

    main{padding:18px 0}
    .grid{
      display:grid;
      grid-template-columns: 1.1fr .9fr;
      gap:14px;
    }
    @media (max-width: 980px){ .grid{grid-template-columns:1fr} }

    .card{
      background: linear-gradient(180deg, rgba(17,24,39,.85), rgba(15,23,42,.75));
      border:1px solid rgba(255,255,255,.08);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      overflow:hidden;
    }
    .card .hd{
      padding:14px 14px 10px;
      border-bottom:1px solid rgba(255,255,255,.06);
      display:flex; align-items:flex-start; justify-content:space-between; gap:10px;
    }
    .card .hd h2{margin:0;font-size:14px}
    .card .hd p{margin:4px 0 0;color:var(--muted);font-size:12px}
    .card .bd{padding:14px}

    .row{display:grid; grid-template-columns:1fr 1fr; gap:10px}
    @media (max-width: 520px){ .row{grid-template-columns:1fr} }

    label{display:block;font-size:12px;color:var(--muted);margin:2px 0 6px}
    input, select, textarea{
      width:100%;
      padding:12px 12px;
      border-radius: 12px;
      border:1px solid rgba(255,255,255,.10);
      background: rgba(2,6,23,.45);
      color: var(--txt);
      outline:none;
    }
    textarea{min-height:90px; resize:vertical}
    input:focus, select:focus, textarea:focus{border-color: rgba(255,77,166,.45)}

    .btns{display:flex; gap:10px; flex-wrap:wrap; margin-top:12px}
    button{
      border:none; cursor:pointer; font-weight:800;
      border-radius: 12px; padding:12px 14px;
      color:white; background: linear-gradient(135deg, var(--brand), var(--brand2));
    }
    button.secondary{
      background: rgba(255,255,255,.08);
      border:1px solid rgba(255,255,255,.10);
      color: var(--txt);
      font-weight:700;
    }
    button.danger{
      background: rgba(239,68,68,.12);
      border:1px solid rgba(239,68,68,.35);
      color: #fecaca;
      font-weight:800;
    }

    .kpi{display:grid; grid-template-columns:1fr 1fr; gap:10px;}
    .kpi .box{
      padding:12px; border-radius: 14px;
      border:1px solid rgba(255,255,255,.08);
      background: rgba(2,6,23,.35);
    }
    .kpi .big{font-size:18px;font-weight:900}
    .kpi .small{font-size:12px;color:var(--muted);margin-top:4px}

    .line{height:1px;background:var(--line);margin:12px 0}
    .muted{color:var(--muted)}
    .mono{font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;}

    table{width:100%; border-collapse:collapse}
    th,td{border-bottom:1px solid rgba(255,255,255,.06); padding:10px 8px; text-align:left; font-size:13px; vertical-align:top}
    th{color:var(--muted); font-weight:700}
    .right{text-align:right}

    .badge{
      display:inline-block; padding:4px 8px; border-radius:999px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(2,6,23,.35);
      color: var(--txt);
      font-size:12px;
      white-space:nowrap;
    }
    .help{
      padding:10px 12px;
      border-radius: 14px;
      border:1px solid rgba(255,255,255,.08);
      background: rgba(2,6,23,.35);
      color: var(--muted);
      font-size:12px;
      white-space:pre-wrap;
    }

    .checkgrid{display:grid; grid-template-columns:1fr; gap:8px;}
    .checkrow{
      display:grid;
      grid-template-columns: 28px 1fr 140px 120px;
      gap:10px;
      align-items:center;
      padding:10px 10px;
      border-radius:14px;
      border:1px solid rgba(255,255,255,.08);
      background: rgba(2,6,23,.30);
    }
    .checkrow .name{font-weight:800; font-size:13px;}
    .checkrow .sub{font-size:12px;color:var(--muted); margin-top:2px;}
    .checkrow input[type="checkbox"]{width:18px;height:18px}
    .checkrow .miniLabel{font-size:12px;color:var(--muted);margin:0 0 6px}
    .checkrow .stack{display:flex; flex-direction:column}
    .checkrow .price{font-weight:800; text-align:right}
    @media (max-width: 520px){
      .checkrow{grid-template-columns:28px 1fr; }
      .checkrow .stack, .checkrow .price{grid-column: 1 / -1;}
      .checkrow .price{text-align:left}
    }

    .pkgPreview{
      display:flex; gap:12px; align-items:flex-start;
      padding:12px; border-radius:14px;
      border:1px solid rgba(255,255,255,.08);
      background: rgba(2,6,23,.30);
    }
    .pkgImg{
      width:84px;height:84px;border-radius:14px; overflow:hidden;
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.06);
      flex: 0 0 auto;
      display:flex; align-items:center; justify-content:center;
      color: var(--muted); font-size:12px;
    }
    .pkgImg img{width:100%;height:100%;object-fit:cover;display:block}
    .pkgMeta{flex:1}
    .pkgMeta .title{font-weight:900}
    .pkgMeta .desc{margin-top:6px;color:var(--muted);font-size:12px;white-space:pre-wrap}
    .pillrow{display:flex;gap:8px;flex-wrap:wrap;margin-top:10px}

    @media print{
      header, .no-print{display:none !important}
      body{background:white;color:#111827}
      .card{box-shadow:none;border:1px solid #e5e7eb;background:white}
      input,select,textarea{border:1px solid #e5e7eb;background:white;color:#111827}
      .muted{color:#374151}
      .help{border:1px solid #e5e7eb;background:#fff;color:#111827}
      .checkrow{border:1px solid #e5e7eb;background:#fff}
      .pkgPreview{border:1px solid #e5e7eb;background:#fff}
      .pkgImg{border:1px solid #e5e7eb;background:#fff}
    }
  </style>
</head>

<body>
<header>
  <div class="wrap">
    <div class="top">
      <div class="brand">
        <div class="logo"></div>
        <div>
          <h1>Cotizador PRO 🎈 v3</h1>
          <div class="sub">Folio · Anticipo/Saldo · Copy · Admin seleccionado · Paquetes con foto · Datos extra</div>
        </div>
      </div>
      <div class="no-print">
        <span class="badge" id="statusBadge">Listo</span>
      </div>
    </div>

    <nav class="no-print">
      <button class="tab active" data-view="cliente">Cliente</button>
      <button class="tab" data-view="paquetes">Paquetes</button>
      <button class="tab" data-view="admin">Admin (Costeo)</button>
      <button class="tab" data-view="catalogos">Catálogos Admin</button>
      <button class="tab" data-view="historial">Historial</button>
      <button class="tab" data-view="ajustes">Ajustes</button>
    </nav>
  </div>
</header>

<main>
  <div class="wrap">

    <section id="view-cliente" class="view">
      <div class="grid">
        <div class="card">
          <div class="hd">
            <div>
              <h2>Información del cliente</h2>
              <p>Datos + paquete + detalles + pago (anticipo/saldo).</p>
            </div>
            <div class="no-print">
              <div class="pillrow">
                <span class="badge mono" id="quoteId"></span>
                <span class="badge" id="estadoBadge">Pendiente</span>
              </div>
            </div>
          </div>

          <div class="bd">
            <div class="row">
              <div>
                <label>Cliente</label>
                <input id="q_cliente" placeholder="Nombre del cliente" />
              </div>
              <div>
                <label>WhatsApp (solo números)</label>
                <input id="q_whats" placeholder="521XXXXXXXXXX" />
              </div>
            </div>

            <div class="row">
              <div>
                <label>Tipo de evento</label>
                <input id="q_evento" placeholder="Cumpleaños, boda, inauguración..." />
              </div>
              <div>
                <label>Fecha del evento</label>
                <input id="q_fecha" type="date" />
              </div>
            </div>

            <div class="row">
              <div>
                <label>Dirección</label>
                <input id="q_direccion" placeholder="Calle, colonia..." />
              </div>
              <div>
                <label>Hora de montaje</label>
                <input id="q_hora" type="time" />
              </div>
            </div>

            <div>
              <label>Ubicación (link de Google Maps)</label>
              <input id="q_ubicacion" placeholder="https://maps.app.goo.gl/..." />
            </div>

            <div class="row">
              <div>
                <label>Paquete</label>
                <select id="q_paquete"></select>
              </div>
              <div>
                <label>Detalle del paquete</label>
                <div class="help" id="paqueteDetalle">Selecciona un paquete para ver su descripción.</div>
              </div>
            </div>

            <div class="pkgPreview" style="margin-top:10px">
              <div class="pkgImg" id="pkgImg">Sin foto</div>
              <div class="pkgMeta">
                <div class="title" id="pkgTitle">—</div>
                <div class="desc" id="pkgDesc">—</div>
                <div class="pillrow">
                  <span class="badge" id="pkgPrice">—</span>
                </div>
              </div>
            </div>

            <div style="margin-top:10px">
              <label>Detalles / Personalización</label>
              <textarea id="q_notas" placeholder="Colores, temática, referencias, etc."></textarea>
            </div>

            <div class="row">
              <div>
                <label>Anticipo ($)</label>
                <input id="q_anticipo" type="number" step="1" min="0" value="0" />
              </div>
              <div>
                <label>Estado</label>
                <select id="q_estado">
                  <option value="Pendiente">Pendiente</option>
                  <option value="Pagado">Pagado</option>
                </select>
              </div>
            </div>

            <div class="btns no-print">
              <button id="btn_guardar">Guardar cotización</button>
              <button class="secondary" id="btn_imprimir">Imprimir / PDF</button>
              <button class="secondary" id="btn_whats">Enviar WhatsApp</button>
              <button class="secondary" id="btn_copy">Copiar mensaje</button>
              <button class="danger" id="btn_limpiar">Limpiar</button>
            </div>
          </div>
        </div>

        <div class="card">
          <div class="hd">
            <div>
              <h2>Resumen</h2>
              <p>Cliente ve precio final + anticipo + saldo.</p>
            </div>
          </div>
          <div class="bd">
            <div class="kpi">
              <div class="box">
                <div class="big" id="k_total">$0.00</div>
                <div class="small">Total</div>
              </div>
              <div class="box">
                <div class="big" id="k_saldo">$0.00</div>
                <div class="small">Saldo</div>
              </div>
              <div class="box">
                <div class="big" id="k_anticipo">$0.00</div>
                <div class="small">Anticipo</div>
              </div>
              <div class="box">
                <div class="big" id="k_paquete">$0.00</div>
                <div class="small">Precio del paquete</div>
              </div>
            </div>

            <div class="line"></div>
            <div class="mono muted" style="font-size:12px; white-space:pre-wrap" id="resumenCliente"></div>

            <div class="line"></div>
            <div class="muted" style="font-size:12px">
              *Tus costos se ven en <b>Admin (Costeo)</b>.
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="view-paquetes" class="view" style="display:none">
      <div class="card">
        <div class="hd">
          <div>
            <h2>Paquetes (editable)</h2>
            <p>Nombre + descripción + precio + foto URL.</p>
          </div>
          <div class="no-print">
            <button class="secondary" id="btn_add_pack">+ Paquete</button>
          </div>
        </div>
        <div class="bd">
          <div id="paquetesTable"></div>
        </div>
      </div>
    </section>

    <section id="view-admin" class="view" style="display:none">
      <div class="grid">

        <div class="card">
          <div class="hd">
            <div>
              <h2>Costeo (checkbox) — Solo tú</h2>
              <p>Selecciona lo que usaste (y cantidades si aplica).</p>
            </div>
          </div>
          <div class="bd">

            <h3 style="margin:0 0 8px;font-size:13px">1) Globo / Material</h3>
            <div id="adminGlobos" class="checkgrid"></div>

            <div class="line"></div>

            <h3 style="margin:0 0 8px;font-size:13px">2) Empleados</h3>
            <div id="adminEmps" class="checkgrid"></div>

            <div class="line"></div>

            <h3 style="margin:0 0 8px;font-size:13px">3) Mobiliario / Rentas</h3>
            <div id="adminRentas" class="checkgrid"></div>

            <div class="line"></div>

            <h3 style="margin:0 0 8px;font-size:13px">4) Otros</h3>
            <div id="adminOtros" class="checkgrid"></div>

            <div class="btns no-print">
              <button class="secondary" id="btn_admin_clear">Limpiar selección Admin</button>
              <button id="btn_guardar_costeo">Guardar costeo en esta cotización</button>
            </div>

            <div class="line"></div>
            <h3 style="margin:0 0 8px;font-size:13px">Seleccionado (reporte rápido)</h3>
            <div class="help" id="adminSeleccionado">—</div>

          </div>
        </div>

        <div class="card">
          <div class="hd">
            <div>
              <h2>Resultado Admin</h2>
              <p>Cuánto te costó y cuánto te dejó.</p>
            </div>
          </div>
          <div class="bd">
            <div class="kpi">
              <div class="box">
                <div class="big" id="a_costos">$0.00</div>
                <div class="small">Costo total</div>
              </div>
              <div class="box">
                <div class="big" id="a_utilidad">$0.00</div>
                <div class="small">Utilidad (Total - Costos)</div>
              </div>
              <div class="box">
                <div class="big" id="a_globos">$0.00</div>
                <div class="small">Globos / material</div>
              </div>
              <div class="box">
                <div class="big" id="a_mano">$0.00</div>
                <div class="small">Mano de obra</div>
              </div>
              <div class="box">
                <div class="big" id="a_rentas">$0.00</div>
                <div class="small">Rentas</div>
              </div>
              <div class="box">
                <div class="big" id="a_otros">$0.00</div>
                <div class="small">Otros</div>
              </div>
            </div>

            <div class="line"></div>
            <div class="mono muted" style="font-size:12px; white-space:pre-wrap" id="adminResumen"></div>
          </div>
        </div>

      </div>
    </section>

    <section id="view-catalogos" class="view" style="display:none">
      <div class="grid">
        <div class="card">
          <div class="hd">
            <div>
              <h2>Catálogo: Globos / Material</h2>
              <p>Editable. Se usa como checkboxes en Admin.</p>
            </div>
            <div class="no-print">
              <button class="secondary" id="btn_add_mat">+ Agregar</button>
            </div>
          </div>
          <div class="bd"><div id="catMat"></div></div>
        </div>

        <div class="card">
          <div class="hd">
            <div>
              <h2>Catálogo: Empleados</h2>
              <p>Editable. Se usa como checkboxes en Admin.</p>
            </div>
            <div class="no-print">
              <button class="secondary" id="btn_add_emp">+ Agregar</button>
            </div>
          </div>
          <div class="bd"><div id="catEmp"></div></div>
        </div>

        <div class="card">
          <div class="hd">
            <div>
              <h2>Catálogo: Mobiliario / Rentas</h2>
              <p>Editable. Se usa como checkboxes en Admin.</p>
            </div>
            <div class="no-print">
              <button class="secondary" id="btn_add_renta">+ Agregar</button>
            </div>
          </div>
          <div class="bd"><div id="catRent"></div></div>
        </div>

        <div class="card">
          <div class="hd">
            <div>
              <h2>Catálogo: Otros</h2>
              <p>Editable. Se usa como checkboxes en Admin.</p>
            </div>
            <div class="no-print">
              <button class="secondary" id="btn_add_otro">+ Agregar</button>
            </div>
          </div>
          <div class="bd"><div id="catOtros"></div></div>
        </div>
      </div>
    </section>

    <section id="view-historial" class="view" style="display:none">
      <div class="card">
        <div class="hd">
          <div>
            <h2>Historial</h2>
            <p>Cotizaciones guardadas en este dispositivo.</p>
          </div>
          <div class="no-print btns" style="margin:0">
            <button class="secondary" id="btn_export">Exportar JSON</button>
            <button class="danger" id="btn_borrar_hist">Borrar historial</button>
          </div>
        </div>
        <div class="bd">
          <div id="histTable"></div>
        </div>
      </div>
    </section>

    <section id="view-ajustes" class="view" style="display:none">
      <div class="card">
        <div class="hd">
          <div>
            <h2>Ajustes</h2>
            <p>Tu info + folios.</p>
          </div>
        </div>
        <div class="bd">
          <div class="row">
            <div>
              <label>Nombre del negocio</label>
              <input id="s_negocio" placeholder="Ej: Decoraciones Herrera" />
            </div>
            <div>
              <label>Ciudad / Zona</label>
              <input id="s_zona" placeholder="Ej: Córdoba, Ver." />
            </div>
          </div>

          <div class="row">
            <div>
              <label>WhatsApp por defecto (521...)</label>
              <input id="s_whats_default" placeholder="521XXXXXXXXXX" />
            </div>
            <div>
              <label>Texto de vigencia</label>
              <input id="s_vigencia" placeholder="Ej: Vigencia 3 días" />
            </div>
          </div>

          <div class="row">
            <div>
              <label>Prefijo de folio</label>
              <input id="s_folio_prefix" placeholder="DH" />
            </div>
            <div>
              <label>Próximo número de folio</label>
              <input id="s_folio_next" type="number" min="1" step="1" />
              <div class="muted" style="font-size:12px;margin-top:6px">Ej: si está en 25, el siguiente folio será DH-000025</div>
            </div>
          </div>

          <div class="btns no-print">
            <button id="btn_save_settings">Guardar ajustes</button>
            <button class="danger" id="btn_reset_all">Restablecer todo</button>
          </div>

          <div class="line"></div>
          <div class="muted" style="font-size:12px">
            Tip: En iPhone, abre la URL en Safari → Compartir → <b>Agregar a pantalla de inicio</b>.
          </div>
        </div>
      </div>
    </section>

  </div>
</main>

<script>
/* -------------------- Storage Keys (v3) -------------------- */
const KEY_SETTINGS = "balloonPack.settings.v3";
const KEY_PACKAGES = "balloonPack.packages.v3";
const KEY_CATALOGS = "balloonPack.catalogs.v3";
const KEY_HISTORY  = "balloonPack.history.v3";

/* -------------------- Helpers -------------------- */
function money(n){
  const v = Number(n||0);
  return v.toLocaleString("es-MX",{style:"currency",currency:"MXN"});
}
function uid(){ return Math.random().toString(36).slice(2,9) + "-" + Date.now().toString(36); }
function load(key, fallback){
  try{ const raw = localStorage.getItem(key); return raw ? JSON.parse(raw) : fallback; }
  catch(e){ return fallback; }
}
function save(key, value){ localStorage.setItem(key, JSON.stringify(value)); }
function setBadge(txt){
  document.getElementById("statusBadge").textContent = txt;
  setTimeout(()=>document.getElementById("statusBadge").textContent="Listo", 1200);
}
function escapeHtml(str){
  return String(str||"").replace(/[&<>"']/g, s=>({ "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#039;" }[s]));
}
function pad6(n){
  const x = String(Math.max(0, Number(n||0)));
  return x.padStart(6,"0");
}

/* -------------------- Defaults -------------------- */
const defaults = {
  settings: {
    negocio: "Decoraciones con Globos",
    zona: "",
    whats_default: "",
    vigencia: "Vigencia 3 días",
    folio_prefix: "DH",
    folio_next: 1
  },
  packages: [
    { id: uid(), nombre: "Paquete Básico", precio: 1500, fotoUrl:"", descripcion: "Incluye: guirnalda orgánica + 2 colores." },
    { id: uid(), nombre: "Paquete Estándar", precio: 2200, fotoUrl:"", descripcion: "Incluye: guirnalda más grande + 3 colores + detalle especial." },
    { id: uid(), nombre: "Paquete Premium", precio: 3500, fotoUrl:"", descripcion: "Incluye: montaje completo + estructura + decoración extra." }
  ],
  catalogs: {
    materiales: [
      { id: uid(), nombre: "Bolsa Sempertex #12", costo: 0, usaCantidad:true },
      { id: uid(), nombre: "Bolsa Sempertex #5",  costo: 0, usaCantidad:true },
      { id: uid(), nombre: "Cinta / Tira orgánica", costo: 0, usaCantidad:false },
    ],
    empleados: [
      { id: uid(), nombre: "Empleado 1", pago: 0 },
      { id: uid(), nombre: "Empleado 2", pago: 0 },
    ],
    rentas: [
      { id: uid(), nombre: "Aro", costo: 0, usaCantidad:false },
      { id: uid(), nombre: "Panel", costo: 0, usaCantidad:false },
      { id: uid(), nombre: "Cilindros", costo: 0, usaCantidad:true },
    ],
    otros: [
      { id: uid(), nombre: "Transporte", costo: 0, usaCantidad:false },
      { id: uid(), nombre: "Flores", costo: 0, usaCantidad:false },
    ]
  },
  history: []
};

/* -------------------- State -------------------- */
let settings = load(KEY_SETTINGS, defaults.settings);
let packages = load(KEY_PACKAGES, defaults.packages);
let catalogs = load(KEY_CATALOGS, defaults.catalogs);
let history  = load(KEY_HISTORY, defaults.history);

let currentQuoteId = uid();
let currentFolio = makeFolioPreview();

function makeFolioPreview(){
  return `${(settings.folio_prefix||"DH").trim()}-${pad6(settings.folio_next||1)}`;
}
function consumeNextFolio(){
  const folio = makeFolioPreview();
  settings.folio_next = Number(settings.folio_next||1) + 1;
  save(KEY_SETTINGS, settings);
  return folio;
}

/* -------------------- UI refs -------------------- */
const quoteIdEl = document.getElementById("quoteId");
const estadoBadge = document.getElementById("estadoBadge");

const q_cliente = document.getElementById("q_cliente");
const q_whats   = document.getElementById("q_whats");
const q_evento  = document.getElementById("q_evento");
const q_fecha   = document.getElementById("q_fecha");
const q_direccion = document.getElementById("q_direccion");
const q_hora = document.getElementById("q_hora");
const q_ubicacion = document.getElementById("q_ubicacion");

const q_paquete = document.getElementById("q_paquete");
const q_notas   = document.getElementById("q_notas");
const q_anticipo= document.getElementById("q_anticipo");
const q_estado  = document.getElementById("q_estado");

const paqueteDetalle = document.getElementById("paqueteDetalle");

const k_total   = document.getElementById("k_total");
const k_paquete = document.getElementById("k_paquete");
const k_anticipo= document.getElementById("k_anticipo");
const k_saldo   = document.getElementById("k_saldo");
const resumenCliente = document.getElementById("resumenCliente");

/* package preview */
const pkgImg = document.getElementById("pkgImg");
const pkgTitle = document.getElementById("pkgTitle");
const pkgDesc = document.getElementById("pkgDesc");
const pkgPrice = document.getElementById("pkgPrice");

/* Admin */
const adminGlobos = document.getElementById("adminGlobos");
const adminEmps   = document.getElementById("adminEmps");
const adminRentas = document.getElementById("adminRentas");
const adminOtros  = document.getElementById("adminOtros");
const adminSeleccionado = document.getElementById("adminSeleccionado");

const a_costos   = document.getElementById("a_costos");
const a_utilidad = document.getElementById("a_utilidad");
const a_globos   = document.getElementById("a_globos");
const a_mano     = document.getElementById("a_mano");
const a_rentas   = document.getElementById("a_rentas");
const a_otros    = document.getElementById("a_otros");
const adminResumen = document.getElementById("adminResumen");

/* Settings */
const s_negocio = document.getElementById("s_negocio");
const s_zona    = document.getElementById("s_zona");
const s_whats_default = document.getElementById("s_whats_default");
const s_vigencia = document.getElementById("s_vigencia");
const s_folio_prefix = document.getElementById("s_folio_prefix");
const s_folio_next = document.getElementById("s_folio_next");

/* Catalog editors */
const catMat   = document.getElementById("catMat");
const catEmp   = document.getElementById("catEmp");
const catRent  = document.getElementById("catRent");
const catOtros = document.getElementById("catOtros");

/* -------------------- Selections -------------------- */
let selections = makeEmptySelections();
function makeEmptySelections(){
  return { materiales:{}, empleados:{}, rentas:{}, otros:{} };
}
function ensureSelectionBucket(catKey){
  const bucket = selections[catKey];
  catalogs[catKey].forEach(item=>{
    if(!bucket[item.id]){
      bucket[item.id] = { checked:false, qty: 1, payOverride: null };
    }
  });
  Object.keys(bucket).forEach(id=>{
    if(!catalogs[catKey].some(x=>x.id===id)) delete bucket[id];
  });
}

function refreshHeaderBadges(){
  quoteIdEl.textContent = `${currentFolio} · ID ${currentQuoteId.split("-")[0].toUpperCase()}`;
}
refreshHeaderBadges();

/* -------------------- Packages -------------------- */
function renderPackageSelect(){
  q_paquete.innerHTML = "";
  packages.forEach(p=>{
    const opt = document.createElement("option");
    opt.value = p.id;
    opt.textContent = `${p.nombre} · ${money(p.precio)}`;
    q_paquete.appendChild(opt);
  });
}
function persistPackages(){ save(KEY_PACKAGES, packages); setBadge("Paquetes guardados"); }
function getSelectedPackage(){
  const id = q_paquete.value;
  return packages.find(x=>x.id===id) || { nombre:"", precio:0, descripcion:"", fotoUrl:"" };
}

function renderPackageTable(){
  const wrap = document.getElementById("paquetesTable");
  wrap.innerHTML = `
    <table>
      <thead>
        <tr>
          <th>Paquete</th>
          <th>Descripción</th>
          <th>Foto URL</th>
          <th class="right">Precio</th>
          <th class="right">Acciones</th>
        </tr>
      </thead>
      <tbody>
        ${packages.map(p=>`
          <tr>
            <td style="min-width:180px">
              <input value="${escapeHtml(p.nombre)}" data-pname="${p.id}">
            </td>
            <td style="min-width:260px">
              <textarea data-pdesc="${p.id}">${escapeHtml(p.descripcion)}</textarea>
            </td>
            <td style="min-width:220px">
              <input value="${escapeHtml(p.fotoUrl||"")}" placeholder="https://..." data-pimg="${p.id}">
              <div class="muted" style="font-size:12px;margin-top:6px">Tip: pega link directo a imagen (JPG/PNG)</div>
            </td>
            <td class="right" style="min-width:140px">
              <input type="number" step="1" min="0" value="${Number(p.precio||0)}" data-pprice="${p.id}">
            </td>
            <td class="right" style="min-width:120px">
              <button class="danger" data-pdel="${p.id}">Eliminar</button>
            </td>
          </tr>
        `).join("")}
      </tbody>
    </table>
  `;

  wrap.querySelectorAll("input[data-pname]").forEach(inp=>{
    inp.addEventListener("input", ()=>{
      const id = inp.getAttribute("data-pname");
      const it = packages.find(x=>x.id===id);
      if(it){ it.nombre = inp.value; persistPackages(); renderPackageSelect(); recalcCliente(); }
    });
  });
  wrap.querySelectorAll("textarea[data-pdesc]").forEach(inp=>{
    inp.addEventListener("input", ()=>{
      const id = inp.getAttribute("data-pdesc");
      const it = packages.find(x=>x.id===id);
      if(it){ it.descripcion = inp.value; persistPackages(); recalcCliente(); }
    });
  });
  wrap.querySelectorAll("input[data-pimg]").forEach(inp=>{
    inp.addEventListener("input", ()=>{
      const id = inp.getAttribute("data-pimg");
      const it = packages.find(x=>x.id===id);
      if(it){ it.fotoUrl = inp.value; persistPackages(); recalcCliente(); }
    });
  });
  wrap.querySelectorAll("input[data-pprice]").forEach(inp=>{
    inp.addEventListener("input", ()=>{
      const id = inp.getAttribute("data-pprice");
      const it = packages.find(x=>x.id===id);
      if(it){ it.precio = Number(inp.value||0); persistPackages(); renderPackageSelect(); recalcCliente(); }
    });
  });
  wrap.querySelectorAll("button[data-pdel]").forEach(btn=>{
    btn.addEventListener("click", ()=>{
      const id = btn.getAttribute("data-pdel");
      packages = packages.filter(x=>x.id!==id);
      persistPackages();
      renderPackageSelect();
      renderPackageTable();
      recalcCliente();
      setBadge("Paquete eliminado");
    });
  });
}

/* -------------------- Cliente calc -------------------- */
function setEstadoUI(estado){
  estadoBadge.textContent = estado;
}
function safeImg(el, url){
  el.innerHTML = "";
  if(!url || !String(url).trim()){
    el.textContent = "Sin foto";
    return;
  }
  const img = document.createElement("img");
  img.src = url;
  img.alt = "Foto paquete";
  img.onerror = ()=>{ el.innerHTML = "<span style='color:var(--muted);font-size:12px'>Foto inválida</span>"; };
  el.appendChild(img);
}

function recalcCliente(){
  const p = getSelectedPackage();
  paqueteDetalle.textContent = (p.descripcion || "Sin descripción.");

  pkgTitle.textContent = p.nombre || "—";
  pkgDesc.textContent = p.descripcion || "—";
  document.getElementById("pkgPrice").textContent = money(p.precio||0);
  safeImg(pkgImg, p.fotoUrl||"");

  const total = Number(p.precio||0);
  const anticipo = Math.max(0, Number(q_anticipo.value||0));
  const saldo = Math.max(0, total - anticipo);

  let estado = q_estado.value || "Pendiente";
  if(saldo <= 0 && total > 0) estado = "Pagado";
  else if(total === 0) estado = "Pendiente";
  q_estado.value = estado;
  setEstadoUI(estado);

  k_total.textContent = money(total);
  k_paquete.textContent = money(p.precio||0);
  k_anticipo.textContent = money(anticipo);
  k_saldo.textContent = money(saldo);

  const negocio = settings.negocio || "Decoraciones con Globos";
  const zona = settings.zona ? `\nZona: ${settings.zona}` : "";
  const vig = settings.vigencia ? `\n${settings.vigencia}` : "";
  const f = q_fecha.value ? q_fecha.value : "";
  const hora = q_hora.value ? q_hora.value : "";

  const msg =
`${negocio} 🎈
Cotización (${currentFolio})

Cliente: ${q_cliente.value||""}
WhatsApp: ${q_whats.value||""}
Evento: ${q_evento.value||""}
Fecha: ${f}
Hora montaje: ${hora}
Dirección: ${q_direccion.value||""}
Ubicación: ${q_ubicacion.value||""}

Paquete: ${p.nombre}
Incluye:
${p.descripcion}

Detalles:
${q_notas.value||""}

TOTAL: ${money(total)}
ANTICIPO: ${money(anticipo)}
SALDO: ${money(saldo)}
ESTADO: ${estado}${zona}${vig}
`.trim();

  resumenCliente.textContent = msg;

  window.__clienteComputed = { total, anticipo, saldo, estado, msg, paquete: p };
  recalcAdmin();
}

/* -------------------- Admin checkboxes -------------------- */
function renderAdminCheckboxes(){
  ensureSelectionBucket("materiales");
  ensureSelectionBucket("empleados");
  ensureSelectionBucket("rentas");
  ensureSelectionBucket("otros");

  adminGlobos.innerHTML = catalogs.materiales.map(m=>{
    const sel = selections.materiales[m.id] || {checked:false, qty:1};
    const qty = Number(sel.qty ?? 1);
    const lineCost = (sel.checked ? (Number(m.costo||0) * (m.usaCantidad ? qty : 1)) : 0);
    return `
      <div class="checkrow">
        <input type="checkbox" data-cat="materiales" data-id="${m.id}" ${sel.checked ? "checked":""} />
        <div>
          <div class="name">${escapeHtml(m.nombre)}</div>
          <div class="sub">${m.usaCantidad ? "Cantidad × costo" : "Costo fijo"}</div>
        </div>
        <div class="stack">
          <div class="miniLabel">${m.usaCantidad ? "Cantidad" : "—"}</div>
          ${m.usaCantidad ? `<input type="number" min="1" step="1" value="${qty}" data-qty="materiales" data-id="${m.id}">` : `<div class="muted">—</div>`}
        </div>
        <div class="price">${money(lineCost)}</div>
      </div>
    `;
  }).join("");

  adminEmps.innerHTML = catalogs.empleados.map(e=>{
    const sel = selections.empleados[e.id] || {checked:false, payOverride:null};
    const pay = (sel.payOverride !== null && sel.payOverride !== undefined) ? Number(sel.payOverride||0) : Number(e.pago||0);
    const lineCost = sel.checked ? pay : 0;
    return `
      <div class="checkrow">
        <input type="checkbox" data-cat="empleados" data-id="${e.id}" ${sel.checked ? "checked":""} />
        <div>
          <div class="name">${escapeHtml(e.nombre)}</div>
          <div class="sub">Pago por evento (editable)</div>
        </div>
        <div class="stack">
          <div class="miniLabel">Pago</div>
          <input type="number" min="0" step="1" value="${pay}" data-pay="empleados" data-id="${e.id}">
        </div>
        <div class="price">${money(lineCost)}</div>
      </div>
    `;
  }).join("");

  adminRentas.innerHTML = catalogs.rentas.map(r=>{
    const sel = selections.rentas[r.id] || {checked:false, qty:1};
    const qty = Number(sel.qty ?? 1);
    const lineCost = sel.checked ? (Number(r.costo||0) * (r.usaCantidad ? qty : 1)) : 0;
    return `
      <div class="checkrow">
        <input type="checkbox" data-cat="rentas" data-id="${r.id}" ${sel.checked ? "checked":""} />
        <div>
          <div class="name">${escapeHtml(r.nombre)}</div>
          <div class="sub">${r.usaCantidad ? "Cantidad × renta" : "Renta fija"}</div>
        </div>
        <div class="stack">
          <div class="miniLabel">${r.usaCantidad ? "Cantidad" : "—"}</div>
          ${r.usaCantidad ? `<input type="number" min="1" step="1" value="${qty}" data-qty="rentas" data-id="${r.id}">` : `<div class="muted">—</div>`}
        </div>
        <div class="price">${money(lineCost)}</div>
      </div>
    `;
  }).join("");

  adminOtros.innerHTML = catalogs.otros.map(o=>{
    const sel = selections.otros[o.id] || {checked:false, qty:1};
    const qty = Number(sel.qty ?? 1);
    const lineCost = sel.checked ? (Number(o.costo||0) * (o.usaCantidad ? qty : 1)) : 0;
    return `
      <div class="checkrow">
        <input type="checkbox" data-cat="otros" data-id="${o.id}" ${sel.checked ? "checked":""} />
        <div>
          <div class="name">${escapeHtml(o.nombre)}</div>
          <div class="sub">${o.usaCantidad ? "Cantidad × costo" : "Costo fijo"}</div>
        </div>
        <div class="stack">
          <div class="miniLabel">${o.usaCantidad ? "Cantidad" : "—"}</div>
          ${o.usaCantidad ? `<input type="number" min="1" step="1" value="${qty}" data-qty="otros" data-id="${o.id}">` : `<div class="muted">—</div>`}
        </div>
        <div class="price">${money(lineCost)}</div>
      </div>
    `;
  }).join("");
}

function syncAdminCheckboxes(){
  renderAdminCheckboxes();
  recalcAdmin();
}

document.addEventListener("change", (e)=>{
  const cb = e.target;
  if(cb && cb.matches('input[type="checkbox"][data-cat]')){
    const cat = cb.getAttribute("data-cat");
    const id  = cb.getAttribute("data-id");
    selections[cat][id].checked = cb.checked;
    renderAdminCheckboxes();
    recalcAdmin();
  }
});
document.addEventListener("input", (e)=>{
  const el = e.target;
  if(el && el.matches('input[data-qty]')){
    const cat = el.getAttribute("data-qty");
    const id  = el.getAttribute("data-id");
    selections[cat][id].qty = Number(el.value||1);
    renderAdminCheckboxes();
    recalcAdmin();
  }
  if(el && el.matches('input[data-pay="empleados"]')){
    const id = el.getAttribute("data-id");
    selections.empleados[id].payOverride = Number(el.value||0);
    renderAdminCheckboxes();
    recalcAdmin();
  }
});

/* -------------------- Admin calc + reporte -------------------- */
function recalcAdmin(){
  let costoMat = 0, costoEmp = 0, costoRent = 0, costoO = 0;

  const matLines = [];
  catalogs.materiales.forEach(m=>{
    const sel = selections.materiales[m.id];
    if(!sel?.checked) return;
    const qty = Number(sel.qty||1);
    const line = Number(m.costo||0) * (m.usaCantidad ? qty : 1);
    costoMat += line;
    matLines.push(`• ${m.nombre}${m.usaCantidad ? ` x${qty}` : ""} = ${money(line)}`);
  });

  const empLines = [];
  catalogs.empleados.forEach(emp=>{
    const sel = selections.empleados[emp.id];
    if(!sel?.checked) return;
    const pay = (sel.payOverride !== null && sel.payOverride !== undefined) ? Number(sel.payOverride||0) : Number(emp.pago||0);
    costoEmp += pay;
    empLines.push(`• ${emp.nombre} = ${money(pay)}`);
  });

  const rentLines = [];
  catalogs.rentas.forEach(r=>{
    const sel = selections.rentas[r.id];
    if(!sel?.checked) return;
    const qty = Number(sel.qty||1);
    const line = Number(r.costo||0) * (r.usaCantidad ? qty : 1);
    costoRent += line;
    rentLines.push(`• ${r.nombre}${r.usaCantidad ? ` x${qty}` : ""} = ${money(line)}`);
  });

  const otherLines = [];
  catalogs.otros.forEach(o=>{
    const sel = selections.otros[o.id];
    if(!sel?.checked) return;
    const qty = Number(sel.qty||1);
    const line = Number(o.costo||0) * (o.usaCantidad ? qty : 1);
    costoO += line;
    otherLines.push(`• ${o.nombre}${o.usaCantidad ? ` x${qty}` : ""} = ${money(line)}`);
  });

  const costos = costoMat + costoEmp + costoRent + costoO;
  const totalCliente = (window.__clienteComputed?.total) ?? 0;
  const utilidad = totalCliente - costos;

  document.getElementById("a_globos").textContent = money(costoMat);
  document.getElementById("a_mano").textContent = money(costoEmp);
  document.getElementById("a_rentas").textContent = money(costoRent);
  document.getElementById("a_otros").textContent = money(costoO);
  document.getElementById("a_costos").textContent = money(costos);
  document.getElementById("a_utilidad").textContent = money(utilidad);

  const p = window.__clienteComputed?.paquete || getSelectedPackage();
  document.getElementById("adminResumen").textContent =
`Folio: ${currentFolio}
Paquete: ${p.nombre}
Total cliente: ${money(totalCliente)}

COSTEO:
- Globo/Material: ${money(costoMat)}
- Mano de obra:   ${money(costoEmp)}
- Rentas:         ${money(costoRent)}
- Otros:          ${money(costoO)}

COSTO TOTAL: ${money(costos)}
UTILIDAD:    ${money(utilidad)}
`.trim();

  const report =
`GLOBOS / MATERIAL
${matLines.length ? matLines.join("\n") : "—"}

EMPLEADOS
${empLines.length ? empLines.join("\n") : "—"}

RENTAS / MOBILIARIO
${rentLines.length ? rentLines.join("\n") : "—"}

OTROS
${otherLines.length ? otherLines.join("\n") : "—"}
`.trim();

  adminSeleccionado.textContent = report;
}

/* -------------------- Catalog editors -------------------- */
function persistCatalogs(){
  save(KEY_CATALOGS, catalogs);
  setBadge("Catálogos guardados");
  syncAdminCheckboxes();
}

function renderCatalogEditor(catKey, targetEl, schema){
  const list = catalogs[catKey] || [];
  targetEl.innerHTML = `
    <table>
      <thead>
        <tr>
          <th>${schema.nameLabel}</th>
          <th class="right">${schema.priceLabel}</th>
          <th class="right">${schema.hasQtyLabel || "Cantidad"}</th>
          <th class="right">Acciones</th>
        </tr>
      </thead>
      <tbody>
        ${list.map(it=>{
          const showQty = !!schema.qtyFlagField;
          return `
            <tr>
              <td><input value="${escapeHtml(it.nombre)}" data-cname="${catKey}" data-id="${it.id}"></td>
              <td class="right"><input type="number" step="1" min="0" value="${Number(it[schema.priceField]||0)}" data-cprice="${catKey}" data-id="${it.id}"></td>
              <td class="right">
                ${showQty
                  ? `<label class="badge" style="cursor:pointer">
                       <input type="checkbox" style="width:auto" ${it[schema.qtyFlagField] ? "checked":""} data-cqtyflag="${catKey}" data-id="${it.id}">
                       usar cantidad
                     </label>`
                  : `<span class="muted">—</span>`
                }
              </td>
              <td class="right"><button class="danger" data-cdel="${catKey}" data-id="${it.id}">Eliminar</button></td>
            </tr>
          `;
        }).join("")}
      </tbody>
    </table>
  `;

  targetEl.querySelectorAll("input[data-cname]").forEach(inp=>{
    inp.addEventListener("input", ()=>{
      const cat = inp.getAttribute("data-cname");
      const id  = inp.getAttribute("data-id");
      const it = catalogs[cat].find(x=>x.id===id);
      if(it){ it.nombre = inp.value; persistCatalogs(); }
    });
  });
  targetEl.querySelectorAll("input[data-cprice]").forEach(inp=>{
    inp.addEventListener("input", ()=>{
      const cat = inp.getAttribute("data-cprice");
      const id  = inp.getAttribute("data-id");
      const it = catalogs[cat].find(x=>x.id===id);
      if(!it) return;
      it[schema.priceField] = Number(inp.value||0);
      persistCatalogs();
    });
  });
  targetEl.querySelectorAll("input[data-cqtyflag]").forEach(inp=>{
    inp.addEventListener("change", ()=>{
      const cat = inp.getAttribute("data-cqtyflag");
      const id  = inp.getAttribute("data-id");
      const it = catalogs[cat].find(x=>x.id===id);
      if(it){ it[schema.qtyFlagField] = !!inp.checked; persistCatalogs(); }
    });
  });
  targetEl.querySelectorAll("button[data-cdel]").forEach(btn=>{
    btn.addEventListener("click", ()=>{
      const cat = btn.getAttribute("data-cdel");
      const id  = btn.getAttribute("data-id");
      catalogs[cat] = catalogs[cat].filter(x=>x.id!==id);
      persistCatalogs();
      renderAllCatalogEditors();
    });
  });
}

function renderAllCatalogEditors(){
  renderCatalogEditor("materiales", catMat,  { nameLabel:"Material", priceLabel:"Costo", priceField:"costo", qtyFlagField:"usaCantidad", hasQtyLabel:"Cantidad" });
  renderCatalogEditor("empleados",  catEmp,  { nameLabel:"Empleado", priceLabel:"Pago",  priceField:"pago", hasQtyLabel:"Cantidad" });
  renderCatalogEditor("rentas",     catRent, { nameLabel:"Pieza",    priceLabel:"Renta", priceField:"costo", qtyFlagField:"usaCantidad", hasQtyLabel:"Cantidad" });
  renderCatalogEditor("otros",      catOtros,{ nameLabel:"Concepto", priceLabel:"Costo", priceField:"costo", qtyFlagField:"usaCantidad", hasQtyLabel:"Cantidad" });
}

/* -------------------- Historial -------------------- */
function renderHistory(){
  const wrap = document.getElementById("histTable");
  if(!history.length){
    wrap.innerHTML = `<div class="muted">Aún no tienes cotizaciones guardadas.</div>`;
    return;
  }
  wrap.innerHTML = `
    <table>
      <thead>
        <tr>
          <th>Fecha</th>
          <th>Folio</th>
          <th>Cliente</th>
          <th>Paquete</th>
          <th class="right">Total</th>
          <th class="right">Saldo</th>
          <th>Estado</th>
          <th class="right">Acciones</th>
        </tr>
      </thead>
      <tbody>
        ${history.slice().reverse().map(h=>{
          const p = packages.find(x=>x.id===h.paqueteId);
          return `
            <tr>
              <td>${escapeHtml(h.createdAt)}</td>
              <td class="mono">${escapeHtml(h.folio||"")}</td>
              <td>${escapeHtml(h.cliente||"")}</td>
              <td>${escapeHtml(p ? p.nombre : "Paquete")}</td>
              <td class="right"><b>${money(h.total||0)}</b></td>
              <td class="right">${money(h.saldo||0)}</td>
              <td><span class="badge">${escapeHtml(h.estado||"Pendiente")}</span></td>
              <td class="right">
                <button class="secondary" data-load="${h.id}">Cargar</button>
                <button class="danger" data-del="${h.id}">Eliminar</button>
              </td>
            </tr>
          `;
        }).join("")}
      </tbody>
    </table>
  `;

  wrap.querySelectorAll("button[data-load]").forEach(btn=>{
    btn.addEventListener("click", ()=>{
      const id = btn.getAttribute("data-load");
      const item = history.find(x=>x.id===id);
      if(item){ loadQuote(item); switchView("cliente"); setBadge("Cotización cargada"); }
    });
  });
  wrap.querySelectorAll("button[data-del]").forEach(btn=>{
    btn.addEventListener("click", ()=>{
      const id = btn.getAttribute("data-del");
      history = history.filter(x=>x.id!==id);
      save(KEY_HISTORY, history);
      renderHistory();
      setBadge("Eliminada");
    });
  });
}

function loadQuote(item){
  currentQuoteId = item.id || uid();
  currentFolio = item.folio || makeFolioPreview();
  refreshHeaderBadges();

  q_cliente.value = item.cliente||"";
  q_whats.value   = item.whats||"";
  q_evento.value  = item.evento||"";
  q_fecha.value   = item.fecha||"";
  q_direccion.value = item.direccion||"";
  q_hora.value = item.hora||"";
  q_ubicacion.value = item.ubicacion||"";

  q_notas.value   = item.notas||"";
  q_paquete.value = item.paqueteId || packages[0]?.id;

  q_anticipo.value = Number(item.anticipo||0);
  q_estado.value = item.estado || "Pendiente";

  selections = item.selections || makeEmptySelections();
  syncAdminCheckboxes();
  recalcCliente();
}

/* -------------------- Settings -------------------- */
function renderSettings(){
  s_negocio.value = settings.negocio || "";
  s_zona.value    = settings.zona || "";
  s_whats_default.value = settings.whats_default || "";
  s_vigencia.value = settings.vigencia || "";
  s_folio_prefix.value = settings.folio_prefix || "DH";
  s_folio_next.value = Number(settings.folio_next||1);
}

/* -------------------- Views -------------------- */
function switchView(name){
  document.querySelectorAll(".tab").forEach(t=>t.classList.toggle("active", t.dataset.view===name));
  document.querySelectorAll(".view").forEach(v=>v.style.display="none");
  document.getElementById("view-"+name).style.display = "";
  if(name==="paquetes") renderPackageTable();
  if(name==="historial") renderHistory();
  if(name==="ajustes") renderSettings();
  if(name==="catalogos") renderAllCatalogEditors();
  if(name==="admin") syncAdminCheckboxes();
}
document.querySelectorAll(".tab").forEach(t=>t.addEventListener("click", ()=>switchView(t.dataset.view)));

/* -------------------- Buttons -------------------- */
document.getElementById("btn_add_pack").addEventListener("click", ()=>{
  packages.push({ id: uid(), nombre:"Nuevo paquete", precio:0, fotoUrl:"", descripcion:"Describe qué incluye este paquete..." });
  persistPackages();
  renderPackageSelect();
  renderPackageTable();
  recalcCliente();
});

document.getElementById("btn_imprimir").addEventListener("click", ()=>window.print());

document.getElementById("btn_limpiar").addEventListener("click", ()=>{
  q_cliente.value=""; q_whats.value=""; q_evento.value=""; q_fecha.value="";
  q_direccion.value=""; q_hora.value=""; q_ubicacion.value="";
  q_notas.value="";
  q_anticipo.value=0;
  q_estado.value="Pendiente";
  q_paquete.value = packages[0]?.id || "";

  selections = makeEmptySelections();
  ensureSelectionBucket("materiales");
  ensureSelectionBucket("empleados");
  ensureSelectionBucket("rentas");
  ensureSelectionBucket("otros");

  currentQuoteId = uid();
  currentFolio = makeFolioPreview();
  refreshHeaderBadges();

  recalcCliente();
  syncAdminCheckboxes();
  setBadge("Limpio");
});

document.getElementById("btn_guardar").addEventListener("click", ()=>{
  recalcCliente();
  const now = new Date();
  const createdAt = now.toLocaleString("es-MX");
  const c = window.__clienteComputed || { total:0, msg:"", anticipo:0, saldo:0, estado:"Pendiente" };

  const exists = history.some(x=>x.id===currentQuoteId);
  if(!exists){
    currentFolio = consumeNextFolio();
    refreshHeaderBadges();
  }

  const item = {
    id: currentQuoteId,
    folio: currentFolio,
    createdAt,

    cliente: q_cliente.value||"",
    whats: q_whats.value||"",
    evento: q_evento.value||"",
    fecha: q_fecha.value||"",
    direccion: q_direccion.value||"",
    hora: q_hora.value||"",
    ubicacion: q_ubicacion.value||"",

    notas: q_notas.value||"",
    paqueteId: q_paquete.value,

    total: c.total,
    anticipo: c.anticipo,
    saldo: c.saldo,
    estado: c.estado,

    msg: c.msg,
    selections: selections
  };

  const idx = history.findIndex(x=>x.id===item.id);
  if(idx >= 0) history[idx] = item;
  else history.push(item);

  save(KEY_HISTORY, history);
  setBadge("Guardado");
  renderHistory();

  currentQuoteId = uid();
  currentFolio = makeFolioPreview();
  refreshHeaderBadges();
});

document.getElementById("btn_whats").addEventListener("click", ()=>{
  recalcCliente();
  const c = window.__clienteComputed;
  const num = (q_whats.value || settings.whats_default || "").trim();
  if(!num){
    alert("Pon el número de WhatsApp del cliente (o define uno por defecto en Ajustes).");
    return;
  }
  const url = "https://wa.me/" + encodeURIComponent(num) + "?text=" + encodeURIComponent(c.msg);
  window.open(url, "_blank");
});

document.getElementById("btn_copy").addEventListener("click", async ()=>{
  recalcCliente();
  const text = (window.__clienteComputed?.msg) || "";
  try{
    if(navigator.clipboard && navigator.clipboard.writeText){
      await navigator.clipboard.writeText(text);
      setBadge("Copiado ✅");
      return;
    }
    const ta = document.createElement("textarea");
    ta.value = text;
    document.body.appendChild(ta);
    ta.select();
    document.execCommand("copy");
    document.body.removeChild(ta);
    setBadge("Copiado ✅");
  }catch(e){
    alert("No se pudo copiar. Puedes seleccionar el texto manualmente.");
  }
});

document.getElementById("btn_export").addEventListener("click", ()=>{
  const data = { settings, packages, catalogs, history };
  const blob = new Blob([JSON.stringify(data,null,2)], {type:"application/json"});
  const a = document.createElement("a");
  a.href = URL.createObjectURL(blob);
  a.download = "cotizador_export_v3.json";
  a.click();
  setBadge("Exportado");
});

document.getElementById("btn_borrar_hist").addEventListener("click", ()=>{
  if(confirm("¿Seguro? Se borrarán todas las cotizaciones guardadas en este dispositivo.")){
    history = [];
    save(KEY_HISTORY, history);
    renderHistory();
    setBadge("Historial borrado");
  }
});

document.getElementById("btn_admin_clear").addEventListener("click", ()=>{
  selections = makeEmptySelections();
  ensureSelectionBucket("materiales");
  ensureSelectionBucket("empleados");
  ensureSelectionBucket("rentas");
  ensureSelectionBucket("otros");
  syncAdminCheckboxes();
  setBadge("Admin limpio");
});

document.getElementById("btn_guardar_costeo").addEventListener("click", ()=>{
  setBadge("Costeo listo (guarda la cotización)");
});

document.getElementById("btn_add_mat").addEventListener("click", ()=>{
  catalogs.materiales.push({ id: uid(), nombre:"Nuevo material", costo:0, usaCantidad:true });
  persistCatalogs(); renderAllCatalogEditors();
});
document.getElementById("btn_add_emp").addEventListener("click", ()=>{
  catalogs.empleados.push({ id: uid(), nombre:"Nuevo empleado", pago:0 });
  persistCatalogs(); renderAllCatalogEditors();
});
document.getElementById("btn_add_renta").addEventListener("click", ()=>{
  catalogs.rentas.push({ id: uid(), nombre:"Nueva pieza", costo:0, usaCantidad:false });
  persistCatalogs(); renderAllCatalogEditors();
});
document.getElementById("btn_add_otro").addEventListener("click", ()=>{
  catalogs.otros.push({ id: uid(), nombre:"Nuevo concepto", costo:0, usaCantidad:false });
  persistCatalogs(); renderAllCatalogEditors();
});

document.getElementById("btn_save_settings").addEventListener("click", ()=>{
  settings.negocio = s_negocio.value || "";
  settings.zona = s_zona.value || "";
  settings.whats_default = s_whats_default.value || "";
  settings.vigencia = s_vigencia.value || "";

  settings.folio_prefix = (s_folio_prefix.value || "DH").trim();
  settings.folio_next = Math.max(1, Number(s_folio_next.value||1));

  save(KEY_SETTINGS, settings);
  currentFolio = makeFolioPreview();
  refreshHeaderBadges();
  setBadge("Ajustes guardados");
  recalcCliente();
});

document.getElementById("btn_reset_all").addEventListener("click", ()=>{
  if(confirm("¿Restablecer TODO? (Ajustes, paquetes, catálogos e historial)")){
    localStorage.removeItem(KEY_SETTINGS);
    localStorage.removeItem(KEY_PACKAGES);
    localStorage.removeItem(KEY_CATALOGS);
    localStorage.removeItem(KEY_HISTORY);
    settings = defaults.settings;
    packages = defaults.packages;
    catalogs = defaults.catalogs;
    history = defaults.history;

    selections = makeEmptySelections();
    currentQuoteId = uid();
    currentFolio = makeFolioPreview();
    refreshHeaderBadges();

    boot();
    setBadge("Restablecido");
  }
});

["input","change"].forEach(evt=>{
  document.addEventListener(evt, (e)=>{
    const ids = ["q_cliente","q_whats","q_evento","q_fecha","q_paquete","q_notas","q_anticipo","q_estado","q_direccion","q_hora","q_ubicacion"];
    if(ids.includes(e.target.id)) recalcCliente();
  }, true);
});

/* -------------------- Boot -------------------- */
function boot(){
  renderPackageSelect();
  renderSettings();
  renderHistory();

  ensureSelectionBucket("materiales");
  ensureSelectionBucket("empleados");
  ensureSelectionBucket("rentas");
  ensureSelectionBucket("otros");

  try{
    const d = new Date();
    const iso = new Date(d.getTime() - d.getTimezoneOffset()*60000).toISOString().slice(0,10);
    if(!q_fecha.value) q_fecha.value = iso;
  }catch(e){}

  if(!q_paquete.value && packages[0]?.id) q_paquete.value = packages[0].id;

  currentFolio = makeFolioPreview();
  refreshHeaderBadges();

  recalcCliente();
  syncAdminCheckboxes();
}
boot();
</script>

<!-- ✅ PWA: registra Service Worker (requiere HTTPS) -->
<script>
  if ("serviceWorker" in navigator) {
    window.addEventListener("load", () => {
      navigator.serviceWorker.register("./service-worker.js").catch(() => {});
    });
  }
</script>

</body>
</html>
