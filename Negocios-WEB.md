<!doctype html>
<html lang="es-SV">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#0b1220">
<meta name="description" content="NEXORA Tech — e-commerce educativo de electrónica y periféricos.">
<title>NEXORA Tech | Electrónica & Periféricos</title>
<style>
:root{
  --bg:#07111f; --panel:#0e1a2b; --panel2:#111f33; --card:#102238; --line:#1d3552;
  --text:#ecf4ff; --muted:#9eb2cb; --accent:#5ee7ff; --accent2:#7c5cff;
  --good:#3fe29d; --warn:#ffd166; --danger:#ff6b7a; --shadow:0 18px 55px rgba(0,0,0,.28);
  --radius:20px;
}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{
  margin:0; font-family:Inter,ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;
  background:radial-gradient(1000px 600px at 75% -10%,rgba(124,92,255,.18),transparent 60%),
             radial-gradient(900px 500px at 0% 20%,rgba(94,231,255,.10),transparent 60%),var(--bg);
  color:var(--text); line-height:1.5;
}
button,input,select,textarea{font:inherit}
button{cursor:pointer}
a{color:inherit;text-decoration:none}
img{max-width:100%;display:block}
.app-shell{min-height:100vh}
.topbar{
  position:sticky;top:0;z-index:50;backdrop-filter:blur(18px);
  background:rgba(7,17,31,.82);border-bottom:1px solid rgba(157,186,219,.12);
}
.nav{
  max-width:1400px;margin:auto;padding:12px 18px;display:flex;gap:14px;align-items:center
}
.brand{display:flex;align-items:center;gap:10px;margin-right:8px}
.logo-mark{
  width:42px;height:42px;border-radius:13px;display:grid;place-items:center;
  background:linear-gradient(135deg,var(--accent),var(--accent2));color:#06101e;
  font-weight:900;box-shadow:0 10px 30px rgba(94,231,255,.2)
}
.brand-text strong{display:block;letter-spacing:.12em;font-size:14px}
.brand-text span{display:block;color:var(--muted);font-size:10px}
.nav-links{display:flex;gap:4px;flex:1;overflow:auto}
.nav-links button,.icon-btn{
  border:0;background:transparent;color:var(--muted);padding:10px 12px;border-radius:12px;white-space:nowrap
}
.nav-links button:hover,.nav-links button.active,.icon-btn:hover{background:rgba(255,255,255,.07);color:var(--text)}
.nav-actions{display:flex;gap:6px;align-items:center}
.cart-badge{position:relative}
.badge{
  position:absolute;right:1px;top:1px;min-width:18px;height:18px;padding:0 5px;border-radius:99px;
  background:var(--accent);color:#06101e;font-size:11px;font-weight:800;display:grid;place-items:center
}
main{max-width:1400px;margin:auto;padding:26px 18px 80px}
.view{display:none}
.view.active{display:block}
.hero{
  border:1px solid var(--line);border-radius:28px;overflow:hidden;padding:44px;
  background:linear-gradient(135deg,rgba(94,231,255,.08),rgba(124,92,255,.10)),var(--panel);
  box-shadow:var(--shadow);position:relative
}
.hero:after{
 content:"";position:absolute;inset:auto -80px -140px auto;width:360px;height:360px;border-radius:50%;
 background:radial-gradient(circle,rgba(94,231,255,.18),transparent 65%);pointer-events:none
}
.hero-grid{display:grid;grid-template-columns:1.3fr .7fr;gap:28px;align-items:center}
.eyebrow{text-transform:uppercase;letter-spacing:.18em;color:var(--accent);font-size:12px;font-weight:800}
h1{font-size:clamp(34px,5vw,64px);line-height:1.02;margin:12px 0}
h2{font-size:clamp(24px,3vw,36px);margin:0 0 8px}
h3{margin:0 0 6px}
p{margin:8px 0;color:var(--muted)}
.hero-card{padding:20px;border:1px solid rgba(255,255,255,.09);border-radius:22px;background:rgba(255,255,255,.03)}
.hero-stats{display:grid;grid-template-columns:repeat(2,1fr);gap:10px;margin-top:20px}
.stat{border:1px solid var(--line);background:rgba(0,0,0,.12);padding:14px;border-radius:16px}
.stat strong{font-size:21px;display:block}
.btn{
 border:1px solid var(--line);background:var(--panel2);color:var(--text);padding:11px 15px;border-radius:12px;
 transition:.18s transform,.18s background,.18s border-color;display:inline-flex;align-items:center;justify-content:center;gap:8px
}
.btn:hover{transform:translateY(-1px);border-color:#31537d;background:#173050}
.btn.primary{background:linear-gradient(135deg,var(--accent),#72b7ff);border-color:transparent;color:#04101c;font-weight:800}
.btn.secondary{background:linear-gradient(135deg,#856dff,#5b46cf);border-color:transparent}
.btn.danger{background:rgba(255,107,122,.12);border-color:rgba(255,107,122,.35);color:#ffb1bb}
.btn.good{background:rgba(63,226,157,.1);border-color:rgba(63,226,157,.35);color:#9effcf}
.btn.ghost{background:transparent}
.btn.small{padding:8px 10px;font-size:13px}
.btn.wide{width:100%}
.toolbar{
 display:grid;grid-template-columns:1.5fr repeat(4,minmax(130px,1fr));gap:10px;padding:14px;margin:22px 0;
 border:1px solid var(--line);border-radius:18px;background:rgba(14,26,43,.76)
}
.field{display:grid;gap:6px}
.field label{font-size:12px;color:var(--muted);font-weight:700}
.field input,.field select,.field textarea{
 width:100%;padding:11px 12px;border-radius:11px;border:1px solid var(--line);background:#091524;color:var(--text);outline:none
}
.field input:focus,.field select:focus,.field textarea:focus{border-color:var(--accent);box-shadow:0 0 0 3px rgba(94,231,255,.09)}
.field textarea{min-height:100px;resize:vertical}
.inline{display:flex;gap:10px;align-items:center;flex-wrap:wrap}
.grid{display:grid;gap:16px}
.products{grid-template-columns:repeat(4,minmax(0,1fr))}
.card{
 background:linear-gradient(180deg,rgba(255,255,255,.025),rgba(255,255,255,.01)),var(--card);
 border:1px solid var(--line);border-radius:18px;overflow:hidden;box-shadow:0 8px 30px rgba(0,0,0,.18)
}
.product-img{aspect-ratio:1.25;background:#08111d;overflow:hidden}
.product-img img{width:100%;height:100%;object-fit:cover;transition:transform .35s}
.card:hover .product-img img{transform:scale(1.03)}
.card-body{padding:15px}
.product-meta{display:flex;justify-content:space-between;gap:10px;align-items:center}
.brand-chip,.pill{
 display:inline-flex;align-items:center;gap:5px;border-radius:99px;padding:5px 9px;font-size:11px;font-weight:800;
 background:rgba(94,231,255,.08);color:#9cefff;border:1px solid rgba(94,231,255,.16)
}
.price{font-size:24px;font-weight:900;margin-top:9px}
.price small{color:var(--muted);font-size:11px;font-weight:600}
.rating{color:#ffd166;font-size:13px}
.stock-good{color:var(--good)} .stock-low{color:var(--warn)} .stock-out{color:var(--danger)}
.card-actions{display:grid;grid-template-columns:1fr auto;gap:8px;margin-top:14px}
.section-head{display:flex;align-items:end;justify-content:space-between;gap:15px;margin:26px 0 12px}
.empty{
 padding:35px;border:1px dashed #355174;border-radius:18px;text-align:center;color:var(--muted);background:rgba(255,255,255,.015)
}
.panel{
 padding:20px;border:1px solid var(--line);border-radius:20px;background:rgba(14,26,43,.78);box-shadow:var(--shadow)
}
.stats-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:12px;margin:18px 0}
.stat-card{padding:16px;border:1px solid var(--line);border-radius:16px;background:var(--panel2)}
.stat-card strong{display:block;font-size:24px}
.table-wrap{overflow:auto;border:1px solid var(--line);border-radius:16px}
table{width:100%;border-collapse:collapse;min-width:760px}
th,td{padding:11px 12px;border-bottom:1px solid var(--line);text-align:left}
th{font-size:12px;color:var(--muted);background:#0b1727;position:sticky;top:0}
td{font-size:13px}
.order-card{display:grid;grid-template-columns:1fr auto;gap:18px}
.timeline{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-top:14px}
.step{padding:10px;border:1px solid var(--line);border-radius:12px;text-align:center;color:var(--muted);font-size:12px}
.step.done{background:rgba(63,226,157,.09);border-color:rgba(63,226,157,.35);color:#a5ffd4}
.step.current{background:rgba(94,231,255,.08);border-color:rgba(94,231,255,.35);color:#a9f3ff}
.form-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
.form-grid .full{grid-column:1/-1}
.drawer,.modal-backdrop{position:fixed;inset:0;z-index:100;display:none}
.drawer.open,.modal-backdrop.open{display:block}
.drawer{background:rgba(0,0,0,.5)}
.drawer-panel{
 position:absolute;right:0;top:0;height:100%;width:min(500px,100%);background:#091524;
 border-left:1px solid var(--line);padding:20px;overflow:auto;box-shadow:-20px 0 55px rgba(0,0,0,.35)
}
.modal-backdrop{background:rgba(0,0,0,.65);padding:18px;overflow:auto}
.modal{
 max-width:760px;margin:3vh auto;background:#0b1727;border:1px solid var(--line);border-radius:20px;padding:22px;box-shadow:var(--shadow)
}
.modal.small{max-width:520px}
.modal-head{display:flex;justify-content:space-between;align-items:center;gap:15px;margin-bottom:15px}
.cart-line{display:grid;grid-template-columns:72px 1fr auto;gap:12px;align-items:center;padding:12px 0;border-bottom:1px solid var(--line)}
.cart-line img{width:72px;height:58px;object-fit:cover;border-radius:10px}
.qty{display:flex;align-items:center;gap:6px}
.qty button{width:28px;height:28px;border-radius:8px;border:1px solid var(--line);background:#0d1a2b;color:var(--text)}
.summary{display:grid;gap:8px;margin-top:14px}
.summary-row{display:flex;justify-content:space-between;gap:14px}
.summary-row.total{padding-top:10px;margin-top:4px;border-top:1px solid var(--line);font-size:20px;font-weight:900}
.notice{
 padding:11px 13px;border-radius:12px;background:rgba(255,209,102,.08);border:1px solid rgba(255,209,102,.22);color:#ffe8a8;font-size:12px
}
.notice.good{background:rgba(63,226,157,.07);border-color:rgba(63,226,157,.22);color:#b0ffda}
.notice.danger{background:rgba(255,107,122,.07);border-color:rgba(255,107,122,.24);color:#ffc0c7}
.toast{
 position:fixed;left:50%;bottom:22px;transform:translateX(-50%) translateY(20px);opacity:0;z-index:200;
 background:#102238;border:1px solid #33537d;border-radius:12px;padding:12px 16px;box-shadow:var(--shadow);transition:.25s;pointer-events:none
}
.toast.show{opacity:1;transform:translateX(-50%) translateY(0)}
footer{max-width:1400px;margin:auto;padding:20px 18px 50px;color:var(--muted);border-top:1px solid var(--line)}
.footer-grid{display:grid;grid-template-columns:1.3fr repeat(3,1fr);gap:22px}
.hero-actions{display:flex;gap:10px;flex-wrap:wrap;margin-top:22px}
.mini-kpi{display:flex;gap:8px;align-items:center;color:var(--muted);font-size:12px}
hr{border:0;border-top:1px solid var(--line);margin:18px 0}
@media(max-width:1100px){
 .products{grid-template-columns:repeat(3,minmax(0,1fr))}
 .toolbar{grid-template-columns:1fr repeat(2,minmax(130px,1fr))}
 .toolbar .field:first-child{grid-column:1/-1}
 .stats-grid{grid-template-columns:repeat(3,1fr)}
 .hero-grid{grid-template-columns:1fr}
}
@media(max-width:760px){
 .nav{padding:10px}.nav-links{order:3;width:100%}.nav{flex-wrap:wrap}.nav-actions{margin-left:auto}
 main{padding:16px 12px 60px}.hero{padding:25px 20px}.products{grid-template-columns:repeat(2,minmax(0,1fr))}
 .toolbar{grid-template-columns:1fr}.toolbar .field:first-child{grid-column:auto}
 .form-grid{grid-template-columns:1fr}.form-grid .full{grid-column:auto}
 .stats-grid{grid-template-columns:repeat(2,1fr)}
 .footer-grid{grid-template-columns:1fr 1fr}.order-card{grid-template-columns:1fr}
}
@media(max-width:470px){
 .products{grid-template-columns:1fr}.stats-grid{grid-template-columns:1fr}
 .footer-grid{grid-template-columns:1fr}.hero h1{font-size:39px}
}
</style>
</head>
<body>
<div class="app-shell">
<header class="topbar">
  <nav class="nav">
    <a class="brand" href="#" onclick="App.showView('store');return false">
      <div class="logo-mark">N</div>
      <div class="brand-text"><strong>NEXORA</strong><span>TECH & PERIFÉRICOS</span></div>
    </a>
    <div class="nav-links">
      <button data-view="store" onclick="App.showView('store')">Tienda</button>
      <button data-view="orders" onclick="App.showView('orders')">Mis pedidos</button>
      <button data-view="account" onclick="App.showView('account')">Login / Registro</button>
      <button data-view="admin" onclick="App.showView('admin')">Admin</button>
      <button data-view="support" onclick="App.showView('support')">Soporte</button>
    </div>
    <div class="nav-actions">
      <button class="icon-btn cart-badge" onclick="App.openCart()" aria-label="Abrir carrito">🛒<span id="cartCount" class="badge">0</span></button>
    </div>
  </nav>
</header>

<main>
<section id="view-store" class="view active">
  <div class="hero">
    <div class="hero-grid">
      <div>
        <div class="eyebrow">Electrónica que sí encaja contigo</div>
        <h1>Tecnología para jugar, crear y trabajar.</h1>
        <p>Catálogo educativo de dispositivos y periféricos con inventario, reseñas, promociones, checkout y seguimiento de pedidos.</p>
        <div class="hero-actions">
          <button class="btn primary" onclick="document.getElementById('catalog').scrollIntoView({behavior:'smooth'})">Explorar catálogo</button>
          <button class="btn" onclick="App.openLogin()">Iniciar sesión</button>
        </div>
        <div class="hero-stats">
          <div class="stat"><strong id="heroProductCount">12</strong><span class="mini-kpi">productos de ejemplo</span></div>
          <div class="stat"><strong>13%</strong><span class="mini-kpi">IVA configurado</span></div>
        </div>
      </div>
      <div class="hero-card">
        <h3>⚡ Oferta destacada</h3>
        <p>Usa el cupón <b style="color:var(--accent)">NEXORA10</b> para 10% de descuento sobre el subtotal.</p>
        <div class="notice good">Precios base + IVA. En producción, configura el tratamiento fiscal exacto según el régimen aplicable y tu documentación tributaria.</div>
      </div>
    </div>
  </div>

  <div id="catalog">
    <div class="section-head">
      <div><h2>Catálogo</h2><p>Busca por marca, categoría, precio o especificaciones.</p></div>
      <span id="resultCount" class="pill">0 resultados</span>
    </div>

    <div class="toolbar">
      <div class="field">
        <label for="q">Buscar</label>
        <input id="q" type="search" placeholder="Ej. RTX, inalámbrico, 2 TB..." oninput="App.renderProducts()">
      </div>
      <div class="field">
        <label for="brand">Marca</label>
        <select id="brand" onchange="App.renderProducts()"><option value="">Todas</option></select>
      </div>
      <div class="field">
        <label for="category">Categoría</label>
        <select id="category" onchange="App.renderProducts()"><option value="">Todas</option></select>
      </div>
      <div class="field">
        <label for="minPrice">Precio mínimo (US$)</label>
        <input id="minPrice" type="number" min="0" step="10" oninput="App.renderProducts()">
      </div>
      <div class="field">
        <label for="maxPrice">Precio máximo (US$)</label>
        <input id="maxPrice" type="number" min="0" step="10" oninput="App.renderProducts()">
      </div>
    </div>

    <div id="productGrid" class="grid products"></div>
  </div>
</section>

<section id="view-orders" class="view">
  <div class="section-head">
    <div><h2>Mis pedidos</h2><p>Seguimiento del estado: procesando → enviado → entregado.</p></div>
    <button class="btn" onclick="App.showView('store')">Seguir comprando</button>
  </div>
  <div id="ordersList" class="grid"></div>
</section>

<section id="view-account" class="view">
  <div class="section-head"><div><h2>Login / Registro de clientes</h2><p>Inicia sesión, crea tu cuenta o recupera el acceso a tu cuenta.</p></div></div>
  <div id="accountPanel"></div>
</section>

<section id="view-admin" class="view">
  <div class="section-head"><div><h2>Panel administrativo</h2><p>Inventario, productos, usuarios, ventas y reportes.</p></div></div>
  <div class="stats-grid">
    <div class="stat-card"><span class="mini-kpi">Ventas hoy</span><strong id="kpiDay">$0</strong></div>
    <div class="stat-card"><span class="mini-kpi">Semana</span><strong id="kpiWeek">$0</strong></div>
    <div class="stat-card"><span class="mini-kpi">Mes</span><strong id="kpiMonth">$0</strong></div>
    <div class="stat-card"><span class="mini-kpi">Trimestre</span><strong id="kpiQuarter">$0</strong></div>
    <div class="stat-card"><span class="mini-kpi">Año</span><strong id="kpiYear">$0</strong></div>
  </div>
  <div class="grid" style="grid-template-columns:1.1fr .9fr;gap:16px">
    <div class="panel">
      <div class="section-head"><div><h3>Inventario</h3><p>Las cantidades se actualizan al confirmar una compra.</p></div><button class="btn primary small" onclick="App.openProductEditor()">+ Producto</button></div>
      <div id="inventoryTable" class="table-wrap"></div>
      <div id="lowStockBox" style="margin-top:12px"></div>
    </div>
    <div class="panel">
      <h3>Reportes</h3><p>Genera un PDF local con ventas agrupadas por período.</p>
      <div class="inline" style="margin:13px 0">
        <button class="btn small" onclick="App.downloadReport('day')">Diario</button>
        <button class="btn small" onclick="App.downloadReport('week')">Semanal</button>
        <button class="btn small" onclick="App.downloadReport('month')">Mensual</button>
        <button class="btn small" onclick="App.downloadReport('quarter')">Trimestral</button>
        <button class="btn small" onclick="App.downloadReport('year')">Anual</button>
      </div>
      <hr>
      <h3>Usuarios registrados</h3>
      <div id="usersTable" class="table-wrap" style="margin-top:12px"></div>
      <hr>
      <button class="btn ghost small" onclick="App.seedDemoAgain()">Restaurar datos de demo</button>
    </div>
  </div>
</section>

<section id="view-support" class="view">
  <div class="section-head"><div><h2>Ayuda y soporte</h2><p>FAQ, contacto y asistencia básica local.</p></div></div>
  <div class="grid" style="grid-template-columns:1fr 1fr">
    <div class="panel">
      <h3>Preguntas frecuentes</h3>
      <details open><summary>¿Los precios incluyen IVA?</summary><p>En esta demo los precios de catálogo son base imponible y el IVA se calcula aparte al 13% para que puedas ver el cálculo.</p></details>
      <details><summary>¿Cómo funciona el rastreo?</summary><p>El pedido guarda una marca de tiempo y uno de tres estados. El administrador puede avanzar el estado para simular la operación logística.</p></details>
      <details><summary>¿Se almacenan los datos?</summary><p>La demo usa localStorage/sessionStorage del navegador. En producción se requiere backend, base de datos y controles de acceso reales.</p></details>
      <details><summary>¿Puedo devolver un producto?</summary><p>Sí: desde el pedido puedes registrar motivo. El flujo queda documentado para revisión.</p></details>
    </div>
    <div class="panel">
      <h3>Contacto</h3>
      <form id="supportForm" class="grid" onsubmit="App.submitSupport(event)">
        <div class="field"><label>Nombre</label><input name="name" required maxlength="80"></div>
        <div class="field"><label>Correo</label><input name="email" type="email" required maxlength="120"></div>
        <div class="field"><label>Asunto</label><input name="subject" required maxlength="120"></div>
        <div class="field"><label>Mensaje</label><textarea name="message" required maxlength="1000"></textarea></div>
        <input type="hidden" name="csrf">
        <button class="btn primary" type="submit">Enviar solicitud</button>
      </form>
      <hr>
      <h3>Asistencia</h3>
      <p id="chatLog" class="notice">NEXORA Assist: Hola. Puedo responder preguntas básicas sobre pedidos, devoluciones, pagos e inventario.</p>
      <div class="inline">
        <input id="chatInput" style="flex:1" placeholder="Escribe una pregunta…" onkeydown="if(event.key==='Enter')App.chat()">
        <button class="btn" onclick="App.chat()">Enviar</button>
      </div>
    </div>
  </div>
  <div class="panel" style="margin-top:16px">
    <h3>Información legal y de seguridad</h3>
    <p>Esta solución es una demo educativa y no constituye una certificación de cumplimiento. Para producción, implementa backend, validación duplicada en servidor, control de acceso, registros de auditoría, HTTPS/TLS con certificado válido, gestión de secretos, proveedor de pagos compatible con PCI DSS, políticas de privacidad, documentación fiscal y revisión jurídica local.</p>
    <p>La Ley de Comercio Electrónico de El Salvador regula relaciones comerciales realizadas por medios electrónicos. La Defensoría del Consumidor publica obligaciones para proveedores de comercio electrónico, incluidas información del proveedor, confidencialidad, seguridad de transacciones, resumen y confirmación de la orden, conservación de información comercial y reglas sobre entregas y reintegros.</p><p>OWASP aplicado en la demo: entradas limitadas y sanitizadas, renderizado escapado para reducir XSS, token CSRF simulado, ausencia de consultas SQL, y notas de producción para usar consultas parametrizadas/ORM. La ausencia de un servidor real impide implementar de verdad controles como autorización en backend, rate limiting y verificación de pagos.</p>
    <p class="mini-kpi">Referencias educativas: Asamblea Legislativa (Ley de Comercio Electrónico, Decreto 463); Defensoría del Consumidor (Ley de Protección al Consumidor y reformas); Ministerio de Hacienda (Ley de IVA).</p>
  </div>
</section>
</main>

<footer>
  <div class="footer-grid">
    <div><h3>NEXORA Tech</h3><p>“Conecta. Crea. Avanza.”</p><p>Demo educativa de e-commerce.</p></div>
    <div><h3>Empresa</h3><p>Identidad comercial: NEXORA Tech, S.A. de C.V. (demo)</p><p>Dirección: San Salvador, El Salvador (demo)</p></div>
    <div><h3>Legales</h3><p>IVA: 13% configurado para esta demo.</p><p>Colón de referencia: ₡8.75 = US$1.</p></div>
    <div><h3>Seguridad</h3><p>OWASP: validación, salida escapada, token CSRF simulado y hash de credenciales demo.</p></div>
  </div>
</footer>
</div>

<div id="cartDrawer" class="drawer" onclick="if(event.target===this)App.closeCart()">
  <div class="drawer-panel">
    <div class="modal-head"><div><h2>Tu carrito</h2><p>Revisa cantidades y descuentos.</p></div><button class="btn small" onclick="App.closeCart()">Cerrar</button></div>
    <div id="cartLines"></div>
    <div id="cartSummary"></div>
    <div style="margin-top:14px" class="grid">
      <div class="field"><label>Cupón</label><div class="inline"><input id="couponInput" placeholder="NEXORA10"><button class="btn small" onclick="App.applyCoupon()">Aplicar</button></div></div>
      <button class="btn primary wide" onclick="App.checkout()">Continuar al pago</button>
    </div>
  </div>
</div>

<div id="modalBackdrop" class="modal-backdrop" onclick="if(event.target===this)App.closeModal()">
  <div id="modal" class="modal"></div>
</div>
<div id="toast" class="toast"></div>

<script>
/* ===========================
   NEXORA TECH — DEMO EDUCATIVA
   Todo funciona en el navegador.
   Para producción, mueve la lógica sensible al servidor.
   =========================== */

const App = (() => {
  const TAX = 0.13;
  const COLON_PER_USD = 8.75;
  const DBKEY = 'nexora_demo_db_v1';
  const SESSION_KEY = 'nexora_demo_session';
  const CSRF_KEY = 'nexora_demo_csrf';
  const LOW_STOCK = 5;

  let db = loadDB();
  let session = readSession();
  let coupon = sessionStorage.getItem('nexora_coupon') || '';
  let currentView = 'store';

  function esc(v){
    return String(v ?? '').replace(/[&<>"']/g, ch => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#039;'}[ch]));
  }
  function sanitize(v,max=200){
    return String(v ?? '').replace(/[\\u0000-\\u001f<>]/g,'').trim().slice(0,max);
  }
  function money(n){ return new Intl.NumberFormat('en-US',{style:'currency',currency:'USD'}).format(Number(n||0)); }
  function colon(n){ return '₡' + Number(n||0).toLocaleString('es-SV',{minimumFractionDigits:2,maximumFractionDigits:2}); }
  function id(prefix='ID'){ return prefix + '-' + Date.now().toString(36).toUpperCase() + '-' + Math.random().toString(36).slice(2,7).toUpperCase(); }
  function nowISO(){ return new Date().toISOString(); }
  function fallbackHash(s){
    /* Fallback educativo para navegadores/restricciones que no expongan Web Crypto en file://. */
    let h1=0x811c9dc5,h2=0x01000193;
    for(let i=0;i<s.length;i++){ const c=s.charCodeAt(i); h1=Math.imul(h1^c,16777619); h2=Math.imul(h2+c,2246822519); }
    return (h1>>>0).toString(16).padStart(8,'0')+(h2>>>0).toString(16).padStart(8,'0')+String(s.length).toString(16);
  }
  async function hashPassword(password){
    /* Hash educativo local. En producción: backend + Argon2id/bcrypt/scrypt + salt + rate limiting. */
    const data=new TextEncoder().encode(String(password));
    if(globalThis.crypto?.subtle){
      const buf=await crypto.subtle.digest('SHA-256',data);
      return Array.from(new Uint8Array(buf)).map(x=>x.toString(16).padStart(2,'0')).join('');
    }
    return 'fallback:'+fallbackHash(String(password));
  }
  async function verifyPassword(password,hash){ return await hashPassword(password) === hash; }
  function getCSRF(){
    let t = sessionStorage.getItem(CSRF_KEY);
    if(!t){ t = crypto.getRandomValues(new Uint32Array(4)).join('-'); sessionStorage.setItem(CSRF_KEY,t); }
    return t;
  }
  function ensureCSRF(){ return getCSRF(); }

  const seedProducts = [
    {id:'P1001',name:'Lenovo IdeaPad Slim 3',brand:'Lenovo',category:'Laptop',price:649.99,stock:8,specs:'Ryzen 7 7735HS, Radeon 680M, 24 GB RAM, 2 TB SSD',img:'https://images.unsplash.com/photo-1496181133206-80ce9b88a853?auto=format&fit=crop&w=1000&q=82',desc:'Portátil de productividad con pantalla de 15", memoria DDR5 y almacenamiento NVMe.',rating:4.8,reviews:126},
    {id:'P1002',name:'ASUS TUF Gaming A15',brand:'ASUS',category:'Laptop',price:899.99,stock:6,specs:'Ryzen 7, RTX 4060, 16 GB RAM, 1 TB SSD, 144 Hz',img:'https://images.unsplash.com/photo-1603302576837-37561b2e2302?auto=format&fit=crop&w=1000&q=82',desc:'Laptop gaming para cargas pesadas, creación de contenido y juegos competitivos.',rating:4.7,reviews:84},
    {id:'P1003',name:'Logitech G Pro X 2',brand:'Logitech',category:'Audio',price:219.99,stock:13,specs:'Wireless LIGHTSPEED, 50 mm, Bluetooth, micrófono desmontable',img:'https://images.unsplash.com/photo-1583394838336-acd977736f90?auto=format&fit=crop&w=1000&q=82',desc:'Audífonos inalámbricos premium orientados a gaming y trabajo remoto.',rating:4.6,reviews:214},
    {id:'P1004',name:'Razer BlackWidow V4',brand:'Razer',category:'Teclado',price:149.99,stock:4,specs:'Mecánico, RGB, USB, switches táctiles, macros',img:'https://images.unsplash.com/photo-1587829741301-dc798b83add3?auto=format&fit=crop&w=1000&q=82',desc:'Teclado mecánico RGB con controles multimedia y personalización avanzada.',rating:4.7,reviews:173},
    {id:'P1005',name:'Logitech G Pro X Superlight 2',brand:'Logitech',category:'Mouse',price:149.99,stock:9,specs:'Wireless, sensor HERO 2, 32000 DPI, 60 g',img:'https://images.unsplash.com/photo-1527814050087-3793815479db?auto=format&fit=crop&w=1000&q=82',desc:'Mouse inalámbrico ultraligero para precisión y baja latencia.',rating:4.8,reviews:190},
    {id:'P1006',name:'Samsung T7 Shield 2 TB',brand:'Samsung',category:'Almacenamiento',price:169.99,stock:11,specs:'2 TB, USB 3.2 Gen 2, hasta 1050 MB/s, IP65',img:'https://images.unsplash.com/photo-1597872200969-2b65d56bd16b?auto=format&fit=crop&w=1000&q=82',desc:'SSD externo compacto y resistente para copias de seguridad y juegos.',rating:4.9,reviews:301},
    {id:'P1007',name:'Elgato Wave:3',brand:'Elgato',category:'Streaming',price:139.99,stock:7,specs:'USB-C, condensador, 24-bit/96 kHz, clipguard',img:'https://images.unsplash.com/photo-1590602847861-f357a9332bbc?auto=format&fit=crop&w=1000&q=82',desc:'Micrófono USB con monitoreo de latencia ultrabaja y control de ganancia.',rating:4.6,reviews:97},
    {id:'P1008',name:'AOC 24G2SP',brand:'AOC',category:'Monitor',price:179.99,stock:5,specs:'24", IPS, 165 Hz, 1 ms, 1080p, Adaptive-Sync',img:'https://images.unsplash.com/photo-1527443224154-c4a3942d3acf?auto=format&fit=crop&w=1000&q=82',desc:'Monitor gaming IPS de alta frecuencia para juegos rápidos y trabajo diario.',rating:4.5,reviews:143},
    {id:'P1009',name:'TP-Link Archer AX55',brand:'TP-Link',category:'Redes',price:119.99,stock:10,specs:'Wi-Fi 6 AX3000, OFDMA, WPA3, 4 antenas',img:'https://images.unsplash.com/photo-1544197150-b99a580bb7a8?auto=format&fit=crop&w=1000&q=82',desc:'Router Wi-Fi 6 con cobertura sólida y funciones de seguridad modernas.',rating:4.4,reviews:88},
    {id:'P1010',name:'JBL Flip 6',brand:'JBL',category:'Audio',price:119.99,stock:12,specs:'Bluetooth 5.1, IP67, 12 h de batería',img:'https://images.unsplash.com/photo-1608043152269-423dbba4e7e1?auto=format&fit=crop&w=1000&q=82',desc:'Altavoz portátil resistente al agua para música y reuniones.',rating:4.7,reviews:266},
    {id:'P1011',name:'Anker 737 Power Bank',brand:'Anker',category:'Energía',price:129.99,stock:3,specs:'24,000 mAh, USB-C PD 140 W, pantalla',img:'https://images.unsplash.com/photo-1609592424743-8f7b9c3edbd4?auto=format&fit=crop&w=1000&q=82',desc:'Batería externa de alta potencia para laptops y dispositivos móviles.',rating:4.5,reviews:71},
    {id:'P1012',name:'Elgato Stream Deck MK.2',brand:'Elgato',category:'Streaming',price:149.99,stock:6,specs:'15 teclas LCD, USB-C, perfiles, macros',img:'https://images.unsplash.com/photo-1550745165-9bc0b252726f?auto=format&fit=crop&w=1000&q=82',desc:'Controlador de atajos para streaming, productividad y automatización.',rating:4.8,reviews:154},
    {id:'P1013',name:'Sony DualSense Wireless Controller',brand:'Sony',category:'Control',price:74.99,stock:14,specs:'Bluetooth, USB-C, hápticos, gatillos adaptativos',img:'https://images.unsplash.com/photo-1605901309584-818e25960a8f?auto=format&fit=crop&w=1000&q=82',desc:'Control inalámbrico para gaming en PC y consolas compatibles.',rating:4.7,reviews:231},
    {id:'P1014',name:'HyperX Alloy Origins',brand:'HyperX',category:'Teclado',price:99.99,stock:10,specs:'Mecánico, RGB, USB-C, estructura de aluminio',img:'https://images.unsplash.com/photo-1541140532154-b024d705b90a?auto=format&fit=crop&w=1000&q=82',desc:'Teclado mecánico compacto con iluminación RGB y construcción sólida.',rating:4.6,reviews:142},
    {id:'P1015',name:'WD_BLACK SN850X 1 TB',brand:'Western Digital',category:'Almacenamiento',price:109.99,stock:8,specs:'NVMe PCIe 4.0, 1 TB, hasta 7300 MB/s',img:'https://images.unsplash.com/photo-1597872200969-2b65d56bd16b?auto=format&fit=crop&w=1000&q=82',desc:'SSD NVMe de alto rendimiento para equipos gaming y estaciones de trabajo.',rating:4.8,reviews:118},
    {id:'P1016',name:'BenQ MOBIUZ EX2510S',brand:'BenQ',category:'Monitor',price:229.99,stock:7,specs:'24.5", IPS, 165 Hz, 1 ms, FreeSync Premium',img:'https://images.unsplash.com/photo-1547394765-185e1e68f34e?auto=format&fit=crop&w=1000&q=82',desc:'Monitor gaming de alta frecuencia con panel IPS y baja latencia.',rating:4.7,reviews:96}
  ];

  const seedTransactions = [
    {id:'TX-1001',orderId:'NX-2026-1001',userId:'U1002',date:'2026-09-22T16:30:00-06:00',subtotal:649.99,tax:84.50,discount:0,total:734.49,status:'entregado'},
    {id:'TX-1002',orderId:'NX-2026-1002',userId:'U1003',date:'2026-09-20T10:05:00-06:00',subtotal:219.99,tax:28.60,discount:21.999,total:226.59,status:'enviado'},
    {id:'TX-1003',orderId:'NX-2026-1003',userId:'U1002',date:'2026-09-12T14:00:00-06:00',subtotal:299.98,tax:39.00,discount:0,total:338.98,status:'entregado'},
    {id:'TX-1004',orderId:'NX-2026-1004',userId:'U1003',date:'2026-08-31T12:40:00-06:00',subtotal:149.99,tax:19.50,discount:0,total:169.49,status:'entregado'},
    {id:'TX-1005',orderId:'NX-2026-1005',userId:'U1002',date:'2026-07-18T08:12:00-06:00',subtotal:179.99,tax:23.40,discount:0,total:203.39,status:'entregado'}
  ];

  function demoHash(p){ return btoa(unescape(encodeURIComponent(p))).split('').reverse().join(''); }
  function loadDB(){
    try{
      const raw = localStorage.getItem(DBKEY);
      if(raw) return JSON.parse(raw);
    }catch(e){}
    /* Passwords seeded as reversible demo verifiers only; login transparently upgrades to SHA-256 on first sign-in. */
    const db0 = {
      products: structuredClone(seedProducts),
      users: [
        {id:'U1001',name:'Admin Demo',email:'admin@nexora.test',role:'admin',hash:demoHash('Admin123!'),createdAt:'2026-09-01T10:00:00-06:00'},
        {id:'U1002',name:'Cliente Demo',email:'cliente@nexora.test',role:'customer',hash:demoHash('demo1234'),createdAt:'2026-09-02T11:00:00-06:00'},
        {id:'U1003',name:'Andrea López',email:'andrea@example.test',role:'customer',hash:demoHash('demo1234'),createdAt:'2026-09-05T13:15:00-06:00'}
      ],
      orders: [
        {id:'NX-2026-1001',userId:'U1002',date:'2026-09-22T16:30:00-06:00',items:[{productId:'P1001',name:'Lenovo IdeaPad Slim 3',qty:1,unit:649.99}],subtotal:649.99,discount:0,tax:84.50,total:734.49,payment:'transfer',status:'entregado',address:'San Salvador, El Salvador',history:[{status:'procesando',at:'2026-09-22T16:30:00-06:00'},{status:'enviado',at:'2026-09-23T08:30:00-06:00'},{status:'entregado',at:'2026-09-24T14:20:00-06:00'}]},
        {id:'NX-2026-1002',userId:'U1003',date:'2026-09-20T10:05:00-06:00',items:[{productId:'P1003',name:'Logitech G Pro X 2',qty:1,unit:219.99}],subtotal:219.99,discount:21.999,tax:28.60,total:226.59,payment:'card',address:'Santa Tecla, La Libertad, El Salvador',status:'enviado',history:[{status:'procesando',at:'2026-09-20T10:05:00-06:00'},{status:'enviado',at:'2026-09-21T09:00:00-06:00'}]}
      ],
      transactions: seedTransactions,
      returns: []
    };
    localStorage.setItem(DBKEY,JSON.stringify(db0));
    return db0;
  }
  function saveDB(){ localStorage.setItem(DBKEY,JSON.stringify(db)); }
  function readSession(){ try{return JSON.parse(sessionStorage.getItem(SESSION_KEY)||'null')}catch(e){return null} }
  function currentUser(){ return session ? db.users.find(u=>u.id===session.userId) : null; }
  function requireLogin(){
    if(!currentUser()){ openLogin(); return false; }
    return true;
  }
  function requireAdmin(){
    if(!requireLogin()) return false;
    if(currentUser().role!=='admin'){ toast('Acceso reservado al administrador demo'); return false; }
    return true;
  }

  function showView(view){
    if(view==='admin' && !requireAdmin()) return;
    currentView=view;
    document.querySelectorAll('.view').forEach(v=>v.classList.remove('active'));
    document.getElementById('view-'+view).classList.add('active');
    document.querySelectorAll('.nav-links button').forEach(b=>b.classList.toggle('active',b.dataset.view===view));
    if(view==='store') renderProducts();
    if(view==='orders') renderOrders();
    if(view==='account') renderAccount();
    if(view==='admin') renderAdmin();
    if(view==='support') document.querySelector('[name=csrf]')?.setAttribute('value',ensureCSRF());
    window.scrollTo({top:0,behavior:'smooth'});
  }

  function renderFilters(){
    const brands=[...new Set(db.products.map(p=>p.brand))].sort();
    const cats=[...new Set(db.products.map(p=>p.category))].sort();
    const brand=document.getElementById('brand'); const category=document.getElementById('category');
    const oldB=brand.value,oldC=category.value;
    brand.innerHTML='<option value="">Todas</option>'+brands.map(x=>`<option>${esc(x)}</option>`).join('');
    category.innerHTML='<option value="">Todas</option>'+cats.map(x=>`<option>${esc(x)}</option>`).join('');
    brand.value=brands.includes(oldB)?oldB:'';
    category.value=cats.includes(oldC)?oldC:'';
    document.getElementById('heroProductCount').textContent=db.products.length;
  }

  function renderProducts(){
    renderFilters();
    const q=sanitize(document.getElementById('q')?.value||'',120).toLowerCase();
    const brand=document.getElementById('brand')?.value||'';
    const cat=document.getElementById('category')?.value||'';
    const min=parseFloat(document.getElementById('minPrice')?.value)||0;
    const max=parseFloat(document.getElementById('maxPrice')?.value)||Infinity;
    const list=db.products.filter(p=>{
      const hay=[p.name,p.brand,p.category,p.specs,p.desc].join(' ').toLowerCase();
      return (!q||hay.includes(q))&&(!brand||p.brand===brand)&&(!cat||p.category===cat)&&p.price>=min&&p.price<=max;
    });
    document.getElementById('resultCount').textContent=`${list.length} resultado${list.length===1?'':'s'}`;
    const grid=document.getElementById('productGrid');
    if(!list.length){ grid.innerHTML='<div class="empty" style="grid-column:1/-1">No hay productos con esos filtros.</div>'; return; }
    grid.innerHTML=list.map(p=>{
      const stockClass=p.stock===0?'stock-out':p.stock<=LOW_STOCK?'stock-low':'stock-good';
      const stars='★'.repeat(Math.round(p.rating))+'☆'.repeat(5-Math.round(p.rating));
      return `<article class="card">
        <div class="product-img"><img loading="lazy" src="${esc(p.img)}" alt="${esc(p.name)}" onerror="this.src='https://picsum.photos/seed/${esc(p.id)}/900/700'"></div>
        <div class="card-body">
          <div class="product-meta"><span class="brand-chip">${esc(p.brand)}</span><span class="${stockClass}">${p.stock===0?'Agotado':p.stock<=LOW_STOCK?`⚠ ${p.stock} disponibles`:`${p.stock} disponibles`}</span></div>
          <h3 style="margin-top:10px">${esc(p.name)}</h3>
          <p>${esc(p.desc)}</p>
          <div class="rating">${stars} <span style="color:var(--muted)">(${p.reviews})</span></div>
          <div class="price">${money(p.price)} <small>+ IVA</small></div>
          <p class="mini-kpi">${esc(p.specs)}</p>
          <div class="card-actions">
            <button class="btn primary" ${p.stock===0?'disabled':''} onclick="App.addToCart('${p.id}')">${p.stock===0?'Agotado':'Agregar al carrito'}</button>
            <button class="btn small" onclick="App.productDetails('${p.id}')">Ver</button>
          </div>
        </div>
      </article>`;
    }).join('');
  }

  function productDetails(pid){
    const p=db.products.find(x=>x.id===pid); if(!p) return;
    openModal(`<div class="modal-head"><div><span class="brand-chip">${esc(p.brand)}</span><h2>${esc(p.name)}</h2></div><button class="btn small" onclick="App.closeModal()">Cerrar</button></div>
      <img src="${esc(p.img)}" alt="${esc(p.name)}" style="width:100%;max-height:320px;object-fit:cover;border-radius:14px" onerror="this.src='https://picsum.photos/seed/${esc(p.id)}/900/700'">
      <div class="form-grid" style="margin-top:15px">
        <div><span class="mini-kpi">Precio base</span><h3>${money(p.price)}</h3></div>
        <div><span class="mini-kpi">Calificación</span><h3>★ ${p.rating}/5</h3></div>
        <div class="full"><span class="mini-kpi">Especificaciones</span><p>${esc(p.specs)}</p></div>
        <div class="full"><span class="mini-kpi">Descripción</span><p>${esc(p.desc)}</p></div>
      </div>
      <button class="btn primary wide" ${p.stock===0?'disabled':''} onclick="App.addToCart('${p.id}');App.closeModal()">Agregar al carrito</button>`);
  }

  function getCart(){ return JSON.parse(localStorage.getItem('nexora_cart')||'[]'); }
  function setCart(c){ localStorage.setItem('nexora_cart',JSON.stringify(c)); renderCartBadge(); }
  function renderCartBadge(){ document.getElementById('cartCount').textContent=getCart().reduce((a,x)=>a+x.qty,0); }
  function addToCart(pid){
    const p=db.products.find(x=>x.id===pid); if(!p) return;
    if(p.stock<=0){ toast('Producto agotado'); return; }
    const c=getCart(); const item=c.find(x=>x.productId===pid);
    if(item){ if(item.qty<p.stock)item.qty++; else {toast('No hay más stock disponible');return;} }
    else c.push({productId:pid,qty:1});
    setCart(c); toast('Agregado al carrito'); renderCart();
  }
  function updateQty(pid,delta){
    const p=db.products.find(x=>x.id===pid), c=getCart(); const item=c.find(x=>x.productId===pid);
    if(!item||!p)return;
    item.qty=Math.max(0,Math.min(p.stock,item.qty+delta));
    setCart(c.filter(x=>x.qty>0)); renderCart();
  }
  function removeCart(pid){ setCart(getCart().filter(x=>x.productId!==pid)); renderCart(); }
  function cartCalc(){
    const items=getCart().map(i=>({i,p:db.products.find(p=>p.id===i.productId)})).filter(x=>x.p);
    const subtotal=items.reduce((s,x)=>s+x.p.price*x.i.qty,0);
    let discount=0;
    if(coupon==='NEXORA10') discount=subtotal*.10;
    if(coupon==='TECNOVIP15' && subtotal>=300) discount=subtotal*.15;
    const taxable=Math.max(0,subtotal-discount);
    const tax=taxable*TAX;
    const total=taxable+tax;
    return {items,subtotal,discount,tax,total};
  }
  function openCart(){ renderCart();document.getElementById('cartDrawer').classList.add('open'); }
  function closeCart(){document.getElementById('cartDrawer').classList.remove('open')}
  function applyCoupon(){
    const c=sanitize(document.getElementById('couponInput').value,30).toUpperCase();
    if(!['NEXORA10','TECNOVIP15',''].includes(c)){toast('Cupón no válido');return}
    if(c==='TECNOVIP15' && cartCalc().subtotal<300){toast('TECNOVIP15 requiere US$300 de subtotal');return}
    coupon=c; sessionStorage.setItem('nexora_coupon',coupon); renderCart(); toast(c?`Cupón ${c} aplicado`:'Cupón eliminado');
  }
  function renderCart(){
    const el=document.getElementById('cartLines'), sum=document.getElementById('cartSummary'); const c=cartCalc();
    if(!c.items.length){el.innerHTML='<div class="empty">Tu carrito está vacío.</div>';sum.innerHTML='';return}
    el.innerHTML=c.items.map(({i,p})=>`<div class="cart-line">
      <img src="${esc(p.img)}" alt="">
      <div><b>${esc(p.name)}</b><div class="mini-kpi">${money(p.price)} c/u · stock ${p.stock}</div>
        <div class="qty" style="margin-top:7px"><button onclick="App.updateQty('${p.id}',-1)">−</button><span>${i.qty}</span><button onclick="App.updateQty('${p.id}',1)">+</button><button class="btn danger small" onclick="App.removeCart('${p.id}')">Eliminar</button></div>
      </div>
      <b>${money(p.price*i.qty)}</b>
    </div>`).join('');
    sum.innerHTML=`<div class="summary">
      <div class="summary-row"><span>Subtotal</span><b>${money(c.subtotal)}</b></div>
      <div class="summary-row"><span>Descuento</span><b>−${money(c.discount)}</b></div>
      <div class="summary-row"><span>IVA 13%</span><b>${money(c.tax)}</b></div>
      <div class="summary-row total"><span>Total</span><b>${money(c.total)}</b></div>
      <div class="mini-kpi">Equivalente colones: ${colon(c.total*COLON_PER_USD)}</div>
    </div>`;
  }

  function checkout(){
    if(!cartsHasStock()) return;
    if(!requireLogin()) return;
    const c=cartCalc(); if(!c.items.length){toast('Carrito vacío');return}
    openModal(`<div class="modal-head"><div><h2>Checkout seguro (demo)</h2><p>Los datos sensibles de tarjeta no se guardan.</p></div><button class="btn small" onclick="App.closeModal()">Cerrar</button></div>
      <form onsubmit="App.submitOrder(event)" class="form-grid">
        <div class="field"><label>Nombre</label><input name="name" value="${esc(currentUser().name)}" required maxlength="80"></div>
        <div class="field"><label>Correo</label><input name="email" value="${esc(currentUser().email)}" type="email" required maxlength="120"></div>
        <div class="field full"><label>Dirección de entrega</label><textarea name="address" required maxlength="300" placeholder="Calle, colonia, municipio, departamento">${esc(currentUser().address||'')}</textarea></div>
        <div class="field"><label>Método de pago</label><select name="payment" onchange="App.togglePayment(this.value)" required><option value="card">Tarjeta de crédito</option><option value="cash">Efectivo contra entrega</option><option value="transfer">Transferencia bancaria</option></select></div>
        <div class="field"><label>Referencia de compra</label><input name="reference" placeholder="Opcional" maxlength="40"></div>
        <div id="paymentExtra" class="full"></div>
        <input type="hidden" name="csrf" value="${ensureCSRF()}">
        <div class="notice full">Al confirmar, se registra un resumen de orden, se descuenta stock y se crea un historial de pedido local. En producción, los pagos deben procesarse fuera del navegador y sin almacenar PAN/CVV.</div>
        <button class="btn primary full" type="submit">Confirmar compra · ${money(c.total)}</button>
      </form>`);
    togglePayment('card');
  }
  function validateOrderServerEquivalent(order,address,payment){
    /* Simula la segunda capa de validación que debería existir en el backend. */
    const cleanAddress=sanitize(address,300);
    const allowedPayments=new Set(['card','cash','transfer']);
    return Boolean(order?.items?.length) && cleanAddress.length>=5 && allowedPayments.has(payment) && Number.isFinite(order.total) && order.total>=0 && order.total<1000000;
  }

  function cartsHasStock(){
    for(const {i,p} of cartCalc().items) if(i.qty>p.stock){toast(`Stock insuficiente para ${p.name}`);return false}
    return true;
  }
  function togglePayment(v){
    const el=document.getElementById('paymentExtra'); if(!el)return;
    if(v==='card') el.innerHTML=`<div class="form-grid">
      <div class="field"><label>Número (demo)</label><input name="cardNumber" inputmode="numeric" autocomplete="off" maxlength="19" placeholder="4111 1111 1111 1111" required></div>
      <div class="field"><label>CVV (demo)</label><input name="cvv" inputmode="numeric" maxlength="4" placeholder="123" required></div>
      <div class="field"><label>Vencimiento</label><input name="expiry" maxlength="5" placeholder="12/30" required></div>
      <div class="field"><label>Titular</label><input name="holder" maxlength="80" required></div>
    </div>`;
    else if(v==='transfer') el.innerHTML=`<div class="notice good">Banco demo: Banco NEXORA · Cuenta 0000-0000-0000. Usa una referencia en producción y valida el abono en servidor.</div>`;
    else el.innerHTML=`<div class="notice">Efectivo contra entrega: confirma que tendrás disponible el total al recibir el pedido.</div>`;
  }

  async function submitOrder(e){
    e.preventDefault();
    const form=new FormData(e.target);
    if(form.get('csrf')!==ensureCSRF()){toast('Solicitud no válida');return}
    const address=sanitize(form.get('address'),300);
    const payment=sanitize(form.get('payment'),20);
    const c=cartCalc();
    if(!c.items.length||!cartsHasStock()) return;
    const items=c.items.map(({i,p})=>({productId:p.id,name:p.name,qty:i.qty,unit:p.price}));
    const orderId='NX-'+new Date().getFullYear()+'-'+Math.floor(1000+Math.random()*9000);
    const order={
      id:orderId,userId:currentUser().id,date:nowISO(),items,subtotal:round(c.subtotal),discount:round(c.discount),tax:round(c.tax),total:round(c.total),
      payment,address,status:'procesando',history:[{status:'procesando',at:nowISO()}]
    };
    if(!validateOrderServerEquivalent(order,address,payment)){toast('Validación de pedido rechazada');return}
    db.products.forEach(p=>{const line=items.find(x=>x.productId===p.id);if(line)p.stock-=line.qty});
    db.orders.unshift(order);
    db.transactions.unshift({id:id('TX'),orderId,userId:currentUser().id,date:order.date,subtotal:order.subtotal,tax:order.tax,discount:order.discount,total:order.total,status:order.status});
    const u=db.users.find(x=>x.id===currentUser().id); if(u)u.address=address;
    saveDB();setCart([]);coupon='';sessionStorage.removeItem('nexora_coupon');closeCart();closeModal();toast('Compra confirmada');
    await invoicePDF(order); showView('orders');
  }

  function round(n){ return Math.round(n*100)/100; }

  function renderOrders(){
    const el=document.getElementById('ordersList'); const u=currentUser();
    if(!u){el.innerHTML='<div class="panel"><p>Inicia sesión para consultar tus pedidos.</p><button class="btn primary" onclick="App.openLogin()">Iniciar sesión</button></div>';return}
    const orders=db.orders.filter(o=>o.userId===u.id);
    if(!orders.length){el.innerHTML='<div class="empty">Todavía no tienes pedidos.</div>';return}
    el.innerHTML=orders.map(o=>{
      const idx=['procesando','enviado','entregado'].indexOf(o.status);
      return `<article class="panel order-card">
        <div>
          <div class="inline"><span class="pill">${esc(o.id)}</span><span class="mini-kpi">${new Date(o.date).toLocaleString('es-SV')}</span></div>
          <h3 style="margin-top:10px">${money(o.total)} · ${esc(o.payment)}</h3>
          <p>${esc(o.items.map(x=>`${x.qty}× ${x.name}`).join(' · '))}</p>
          <p>Entrega: ${esc(o.address)}</p>
          <div class="timeline">${['procesando','enviado','entregado'].map((s,i)=>`<div class="step ${i<idx?'done':i===idx?'current':''}">${i<idx?'✓ ':''}${s[0].toUpperCase()+s.slice(1)}</div>`).join('')}</div>
        </div>
        <div class="grid">
          <button class="btn small" onclick="App.downloadInvoice('${o.id}')">Factura PDF</button>
          <button class="btn small" onclick="App.openReturn('${o.id}')">Solicitar devolución</button>
          ${u.role==='admin'?`<button class="btn small good" onclick="App.advanceOrder('${o.id}')">Avanzar estado</button>`:''}
        </div>
      </article>`;
    }).join('');
  }

  function advanceOrder(oid){
    if(!requireAdmin())return;
    const o=db.orders.find(x=>x.id===oid);if(!o)return;
    const states=['procesando','enviado','entregado'];const i=states.indexOf(o.status);
    if(i<states.length-1){o.status=states[i+1];o.history.push({status:o.status,at:nowISO()});}
    const tx=db.transactions.find(t=>t.orderId===oid);if(tx)tx.status=o.status;
    saveDB();renderOrders();renderAdmin();toast(`Pedido ${oid}: ${o.status}`);
  }

  function openReturn(oid){
    const o=db.orders.find(x=>x.id===oid);if(!o)return;
    openModal(`<div class="modal-head"><div><h2>Solicitud de devolución</h2><p>${esc(oid)}</p></div><button class="btn small" onclick="App.closeModal()">Cerrar</button></div>
      <form onsubmit="App.submitReturn(event,'${oid}')" class="grid">
        <div class="field"><label>Motivo</label><select name="reason" required><option value="">Selecciona</option><option>Producto defectuoso</option><option>Producto diferente a lo solicitado</option><option>Pedido no entregado</option><option>Otro</option></select></div>
        <div class="field"><label>Detalle</label><textarea name="detail" maxlength="700" required></textarea></div>
        <input type="hidden" name="csrf" value="${ensureCSRF()}">
        <button class="btn primary" type="submit">Registrar devolución</button>
      </form>`);
  }
  function submitReturn(e,oid){
    e.preventDefault();const f=new FormData(e.target);
    if(f.get('csrf')!==ensureCSRF()){toast('Solicitud no válida');return}
    db.returns.push({id:id('RET'),orderId:oid,userId:currentUser().id,reason:sanitize(f.get('reason'),80),detail:sanitize(f.get('detail'),700),date:nowISO(),status:'recibida'});
    saveDB();closeModal();toast('Solicitud de devolución registrada');
  }

  function renderAccount(){
    const el=document.getElementById('accountPanel');const u=currentUser();
    if(!u){el.innerHTML=`<div class="grid" style="grid-template-columns:1.2fr .8fr;gap:16px">
      <div class="panel"><h3>Iniciar sesión</h3><p>Accede a tus pedidos, carrito guardado y datos de cliente.</p><div class="hero-actions"><button class="btn primary" onclick="App.openLogin()">Iniciar sesión</button><button class="btn" onclick="App.openRegister()">Crear cuenta</button></div><button class="btn ghost small" style="margin-top:10px" onclick="App.openRecovery()">¿Olvidaste tu contraseña?</button></div>
      <div class="panel"><h3>¿Nuevo cliente?</h3><p>Regístrate gratis para guardar tus pedidos y agilizar tus compras.</p><button class="btn primary wide" onclick="App.openRegister()">Registrarme ahora</button><div class="notice" style="margin-top:14px">Demo: cliente@nexora.test / demo1234 · admin@nexora.test / Admin123!</div></div>
    </div>`;return}
    el.innerHTML=`<div class="grid" style="grid-template-columns:1fr 1fr">
      <div class="panel"><h3>${esc(u.name)}</h3><p>${esc(u.email)}</p><p>Rol: <b>${esc(u.role)}</b></p><div class="inline"><button class="btn" onclick="App.logout()">Cerrar sesión</button><button class="btn" onclick="App.editProfile()">Editar perfil</button></div></div>
      <div class="panel"><h3>Seguridad</h3><p>La contraseña de la demo se verifica mediante hash SHA-256 en el navegador. Esto no reemplaza un sistema de autenticación de servidor.</p><button class="btn" onclick="App.openRecovery()">Recuperar contraseña</button></div>
    </div>`;
  }

  function openLogin(){
    openModal(`<div class="modal-head"><div><h2>Iniciar sesión</h2><p>Acceso local de demostración.</p></div><button class="btn small" onclick="App.closeModal()">Cerrar</button></div>
      <form onsubmit="App.login(event)" class="grid">
        <div class="field"><label>Correo</label><input name="email" type="email" autocomplete="username" required maxlength="120"></div>
        <div class="field"><label>Contraseña</label><input name="password" type="password" autocomplete="current-password" required maxlength="128"></div>
        <input type="hidden" name="csrf" value="${ensureCSRF()}">
        <button class="btn primary" type="submit">Entrar</button>
      </form>
      <div class="inline" style="margin-top:10px"><button class="btn small" onclick="App.openRegister()">Registrarme</button><button class="btn small" onclick="App.openRecovery()">Olvidé mi contraseña</button></div>
      <div class="notice" style="margin-top:12px">Demo: cliente@nexora.test / demo1234 · admin@nexora.test / Admin123!</div>`);
  }

  async function login(e){
    e.preventDefault();const f=new FormData(e.target);
    if(f.get('csrf')!==ensureCSRF()){toast('Solicitud no válida');return}
    const email=sanitize(f.get('email'),120).toLowerCase();const pwd=String(f.get('password')||'');
    const u=db.users.find(x=>x.email.toLowerCase()===email);
    if(!u){toast('Credenciales no válidas');return}
    let ok=false;
    /* Upgrade automático del verificador demo a SHA-256. */
    if(u.hash.startsWith('sha256:')) ok=await verifyPassword(pwd,u.hash.slice(7));
    else if(demoHash(pwd)===u.hash){ok=true;u.hash='sha256:'+await hashPassword(pwd);saveDB();}
    if(!ok){toast('Credenciales no válidas');return}
    session={userId:u.id,loginAt:nowISO()};sessionStorage.setItem(SESSION_KEY,JSON.stringify(session));closeModal();toast(`Bienvenido, ${u.name}`);
    renderAccount();renderOrders();
  }

  function logout(){session=null;sessionStorage.removeItem(SESSION_KEY);showView('store');toast('Sesión cerrada');}
  function openRegister(){
    openModal(`<div class="modal-head"><div><h2>Crear cuenta</h2><p>Registro opcional para la demo.</p></div><button class="btn small" onclick="App.closeModal()">Cerrar</button></div>
      <form onsubmit="App.register(event)" class="form-grid">
        <div class="field"><label>Nombre</label><input name="name" required maxlength="80"></div>
        <div class="field"><label>Correo</label><input name="email" type="email" required maxlength="120"></div>
        <div class="field"><label>Contraseña</label><input name="password" type="password" required minlength="8" maxlength="128"></div>
        <div class="field"><label>Confirmar</label><input name="confirm" type="password" required minlength="8" maxlength="128"></div>
        <input type="hidden" name="csrf" value="${ensureCSRF()}">
        <button class="btn primary full" type="submit">Crear cuenta</button>
      </form>`);
  }
  async function register(e){
    e.preventDefault();const f=new FormData(e.target);
    if(f.get('csrf')!==ensureCSRF()){toast('Solicitud no válida');return}
    const name=sanitize(f.get('name'),80),email=sanitize(f.get('email'),120).toLowerCase(),pwd=String(f.get('password')||''),conf=String(f.get('confirm')||'');
    if(!/^[^\\s@]+@[^\\s@]+\\.[^\\s@]+$/.test(email)||pwd.length<8||pwd!==conf){toast('Revisa los datos');return}
    if(db.users.some(u=>u.email.toLowerCase()===email)){toast('Ese correo ya está registrado');return}
    const u={id:id('USR'),name,email,role:'customer',hash:'sha256:'+await hashPassword(pwd),createdAt:nowISO()};
    db.users.push(u);saveDB();session={userId:u.id,loginAt:nowISO()};sessionStorage.setItem(SESSION_KEY,JSON.stringify(session));closeModal();toast('Cuenta creada');renderAccount();
  }
  function openRecovery(){
    openModal(`<div class="modal-head"><div><h2>Recuperación</h2><p>Flujo educativo: no se envían correos reales.</p></div><button class="btn small" onclick="App.closeModal()">Cerrar</button></div>
      <form onsubmit="App.recovery(event)" class="grid"><div class="field"><label>Correo</label><input name="email" type="email" required></div><input type="hidden" name="csrf" value="${ensureCSRF()}"><button class="btn primary">Solicitar enlace</button></form>
      <div class="notice" style="margin-top:12px">En producción: token aleatorio de un solo uso, expiración corta, respuesta genérica y envío por canal verificado.</div>`);
  }
  function recovery(e){e.preventDefault();closeModal();toast('Si el correo existe, recibirás instrucciones de recuperación (demo).');}
  function editProfile(){
    const u=currentUser();if(!u)return;
    openModal(`<div class="modal-head"><div><h2>Editar perfil</h2></div><button class="btn small" onclick="App.closeModal()">Cerrar</button></div>
      <form onsubmit="App.saveProfile(event)" class="grid">
        <div class="field"><label>Nombre</label><input name="name" value="${esc(u.name)}" maxlength="80" required></div>
        <div class="field"><label>Dirección</label><textarea name="address" maxlength="300">${esc(u.address||'')}</textarea></div>
        <input type="hidden" name="csrf" value="${ensureCSRF()}"><button class="btn primary">Guardar</button>
      </form>`);
  }
  function saveProfile(e){e.preventDefault();const f=new FormData(e.target);if(f.get('csrf')!==ensureCSRF())return;const u=currentUser();u.name=sanitize(f.get('name'),80);u.address=sanitize(f.get('address'),300);saveDB();closeModal();renderAccount();toast('Perfil actualizado');}

  function renderAdmin(){
    if(!requireAdmin())return;
    const sums = periodSummary();
    ['Day','Week','Month','Quarter','Year'].forEach(k=>document.getElementById('kpi'+k).textContent=money(sums[k.toLowerCase()]));
    const inv=document.getElementById('inventoryTable');
    inv.innerHTML=`<table><thead><tr><th>Producto</th><th>Marca</th><th>Stock</th><th>Precio</th><th>Acciones</th></tr></thead><tbody>${db.products.map(p=>`<tr>
      <td>${esc(p.name)}</td><td>${esc(p.brand)}</td><td class="${p.stock<=LOW_STOCK?'stock-low':'stock-good'}">${p.stock}</td><td>${money(p.price)}</td>
      <td><div class="inline"><button class="btn small" onclick="App.openProductEditor('${p.id}')">Editar</button><button class="btn danger small" onclick="App.deleteProduct('${p.id}')">Eliminar</button></div></td>
    </tr>`).join('')}</tbody></table>`;
    const lows=db.products.filter(p=>p.stock<=LOW_STOCK);
    document.getElementById('lowStockBox').innerHTML=lows.length?`<div class="notice danger"><b>Alertas:</b> ${lows.map(p=>`${esc(p.name)} (${p.stock})`).join(' · ')}</div>`:'<div class="notice good">No hay alertas de stock bajo.</div>';
    document.getElementById('usersTable').innerHTML=`<table><thead><tr><th>Nombre</th><th>Correo</th><th>Rol</th><th>Creado</th></tr></thead><tbody>${db.users.map(u=>`<tr><td>${esc(u.name)}</td><td>${esc(u.email)}</td><td>${esc(u.role)}</td><td>${new Date(u.createdAt).toLocaleDateString('es-SV')}</td></tr>`).join('')}</tbody></table>`;
  }

  function periodSummary(){
    const now=new Date();const totals={day:0,week:0,month:0,quarter:0,year:0};
    for(const t of db.transactions){
      const d=new Date(t.date);if(d>now)continue;
      const diff=now-d;
      if(diff<=864e5)totals.day+=t.total;
      if(diff<=7*864e5)totals.week+=t.total;
      if(d.getFullYear()===now.getFullYear()&&d.getMonth()===now.getMonth())totals.month+=t.total;
      const qNow=Math.floor(now.getMonth()/3), qD=Math.floor(d.getMonth()/3);
      if(d.getFullYear()===now.getFullYear()&&qNow===qD)totals.quarter+=t.total;
      if(d.getFullYear()===now.getFullYear())totals.year+=t.total;
    }
    return totals;
  }

  function openProductEditor(pid=''){
    if(!requireAdmin())return;const p=db.products.find(x=>x.id===pid)||{id:'',name:'',brand:'',category:'',price:0,stock:0,specs:'',img:'',desc:'',rating:5,reviews:0};
    openModal(`<div class="modal-head"><div><h2>${pid?'Editar producto':'Agregar producto'}</h2><p>Los datos se validan y se almacenan localmente.</p></div><button class="btn small" onclick="App.closeModal()">Cerrar</button></div>
      <form onsubmit="App.saveProduct(event,'${esc(pid)}')" class="form-grid">
        <div class="field"><label>Nombre</label><input name="name" value="${esc(p.name)}" required maxlength="120"></div>
        <div class="field"><label>Marca</label><input name="brand" value="${esc(p.brand)}" required maxlength="60"></div>
        <div class="field"><label>Categoría</label><input name="category" value="${esc(p.category)}" required maxlength="60"></div>
        <div class="field"><label>Precio base USD</label><input name="price" type="number" step="0.01" min="0" value="${p.price}" required></div>
        <div class="field"><label>Stock</label><input name="stock" type="number" min="0" step="1" value="${p.stock}" required></div>
        <div class="field"><label>Rating</label><input name="rating" type="number" min="0" max="5" step="0.1" value="${p.rating}" required></div>
        <div class="field full"><label>URL de imagen</label><input name="img" type="url" value="${esc(p.img)}" required maxlength="500"></div>
        <div class="field full"><label>Especificaciones</label><input name="specs" value="${esc(p.specs)}" required maxlength="300"></div>
        <div class="field full"><label>Descripción</label><textarea name="desc" required maxlength="800">${esc(p.desc)}</textarea></div>
        <input type="hidden" name="csrf" value="${ensureCSRF()}">
        <button class="btn primary full">Guardar producto</button>
      </form>`);
  }
  function saveProduct(e,pid){
    e.preventDefault();const f=new FormData(e.target);if(f.get('csrf')!==ensureCSRF()){toast('Solicitud no válida');return}
    const data={name:sanitize(f.get('name'),120),brand:sanitize(f.get('brand'),60),category:sanitize(f.get('category'),60),price:round(Number(f.get('price'))),stock:Math.max(0,Math.floor(Number(f.get('stock')))),rating:Math.max(0,Math.min(5,Number(f.get('rating')))),img:sanitize(f.get('img'),500),specs:sanitize(f.get('specs'),300),desc:sanitize(f.get('desc'),800)};
    if(!Number.isFinite(data.price)||data.price<0||!Number.isFinite(data.stock)){toast('Valores numéricos inválidos');return}
    if(pid){const p=db.products.find(x=>x.id===pid);Object.assign(p,data)}
    else db.products.push({id:id('P'),reviews:0,...data});
    saveDB();closeModal();renderProducts();renderAdmin();toast(pid?'Producto actualizado':'Producto creado');
  }
  function deleteProduct(pid){
    if(!requireAdmin())return;const p=db.products.find(x=>x.id===pid);if(!p)return;
    if(!confirm(`Eliminar ${p.name}?`))return;
    db.products=db.products.filter(x=>x.id!==pid);saveDB();renderProducts();renderAdmin();toast('Producto eliminado');
  }

  function downloadInvoice(oid){const o=db.orders.find(x=>x.id===oid);if(o)invoicePDF(o)}
  async function invoicePDF(o){
    const lines=[
      'NEXORA TECH — FACTURA DEMO','Conecta. Crea. Avanza.','',
      `Factura: ${o.id}`,`Fecha: ${new Date(o.date).toLocaleString('es-SV')}`,`Cliente: ${currentUser()?.name||'Cliente'}`,
      `Metodo de pago: ${o.payment}`,'', 'DETALLE'
    ];
    o.items.forEach(i=>lines.push(`${i.qty} x ${i.name} — ${money(i.unit)} c/u — ${money(i.qty*i.unit)}`));
    lines.push('',`Subtotal: ${money(o.subtotal)}`,`Descuento: -${money(o.discount)}`,`IVA 13%: ${money(o.tax)}`,`TOTAL USD: ${money(o.total)}`,`TOTAL COLONES: ${colon(o.total*COLON_PER_USD)}`,'',
      'Nota: documento generado por una demo educativa. No sustituye una factura fiscal oficial ni certifica cumplimiento tributario.');
    downloadBlob(makePDF(lines),'factura-'+o.id+'.pdf','application/pdf');
  }

  function periodLabel(kind){
    return ({day:'diario',week:'semanal',month:'mensual',quarter:'trimestral',year:'anual'})[kind]||kind;
  }
  function downloadReport(kind){
    if(!requireAdmin())return;
    const now=new Date();const tx=db.transactions.filter(t=>withinPeriod(new Date(t.date),kind,now));
    const total=tx.reduce((s,t)=>s+t.total,0);
    const lines=['NEXORA TECH — REPORTE DE VENTAS DEMO',`Periodo: ${periodLabel(kind)}`,`Generado: ${now.toLocaleString('es-SV')}`,'',`Transacciones: ${tx.length}`,`Ventas: ${money(total)}`,'', 'TRANSACCIONES'];
    tx.forEach(t=>lines.push(`${t.orderId} | ${new Date(t.date).toLocaleDateString('es-SV')} | ${money(t.total)} | ${t.status}`));
    lines.push('', 'Documento educativo. Verifica requisitos fiscales y contables antes de usar un sistema real.');
    downloadBlob(makePDF(lines),'reporte-'+kind+'.pdf','application/pdf');
  }
  function withinPeriod(d,k,n){
    const diff=n-d;
    if(k==='day')return diff<=864e5;
    if(k==='week')return diff<=7*864e5;
    if(k==='month')return d.getFullYear()===n.getFullYear()&&d.getMonth()===n.getMonth();
    if(k==='quarter')return d.getFullYear()===n.getFullYear()&&Math.floor(d.getMonth()/3)===Math.floor(n.getMonth()/3);
    if(k==='year')return d.getFullYear()===n.getFullYear();
    return false;
  }

  /* PDF mínimo de una sola página: texto Helvetica, sin librerías externas. */
  function pdfSafe(s){
    return String(s).normalize('NFD').replace(/[\\u0300-\\u036f]/g,'')
      .replace(/[€£¥]/g,'').replace(/[–—]/g,'-').replace(/₡/g,'CRC ')
      .replace(/\\/g,'\\\\').replace(/\(/g,'\\(').replace(/\)/g,'\\)');
  }
  function makePDF(lines){
    const width=612,height=792, margin=46, lineH=16;
    const shown=lines.slice(0,42);
    const content=['BT','/F1 10 Tf',`${margin} ${height-margin} Td`];
    shown.forEach((line,i)=>{ if(i>0)content.push(`0 -${lineH} Td`); content.push(`(${pdfSafe(line).slice(0,110)}) Tj`); });
    content.push('ET');
    const stream=content.join('\\n');
    const objs=[];
    objs.push('<< /Type /Catalog /Pages 2 0 R >>');
    objs.push('<< /Type /Pages /Kids [3 0 R] /Count 1 >>');
    objs.push('<< /Type /Page /Parent 2 0 R /MediaBox [0 0 612 792] /Resources << /Font << /F1 5 0 R >> >> /Contents 4 0 R >>');
    objs.push(`<< /Length ${stream.length} >>\\nstream\\n${stream}\\nendstream`);
    objs.push('<< /Type /Font /Subtype /Type1 /BaseFont /Helvetica >>');
    let pdf='%PDF-1.4\\n', offsets=[0];
    objs.forEach((o,i)=>{offsets[i+1]=pdf.length;pdf+=`${i+1} 0 obj\\n${o}\\nendobj\\n`;});
    const xref=pdf.length;pdf+='xref\\n0 '+(objs.length+1)+'\\n0000000000 65535 f \\n';
    for(let i=1;i<=objs.length;i++)pdf+=String(offsets[i]).padStart(10,'0')+' 00000 n \\n';
    pdf+=`trailer\\n<< /Size ${objs.length+1} /Root 1 0 R >>\\nstartxref\\n${xref}\\n%%EOF`;
    return new Blob([pdf],{type:'application/pdf'});
  }
  function downloadBlob(blob,name,type){
    const url=URL.createObjectURL(new Blob([blob],{type}));const a=document.createElement('a');a.href=url;a.download=name;a.click();
    setTimeout(()=>URL.revokeObjectURL(url),1500);
  }

  function submitSupport(e){
    e.preventDefault();const f=new FormData(e.target);
    if(f.get('csrf')!==ensureCSRF()){toast('Solicitud no válida');return}
    const ticket={id:id('SUP'),date:nowISO(),name:sanitize(f.get('name'),80),email:sanitize(f.get('email'),120),subject:sanitize(f.get('subject'),120),message:sanitize(f.get('message'),1000)};
    const all=JSON.parse(localStorage.getItem('nexora_support')||'[]');all.push(ticket);localStorage.setItem('nexora_support',JSON.stringify(all));
    e.target.reset();e.target.querySelector('[name=csrf]').value=ensureCSRF();toast(`Solicitud ${ticket.id} enviada`);
  }
  function chat(){
    const input=document.getElementById('chatInput');const q=sanitize(input.value,200).toLowerCase();if(!q)return;
    let a='Puedo ayudarte con preguntas básicas sobre pedidos, pagos, devoluciones o inventario.';
    if(/pedido|rastreo|envio/.test(q))a='Para ver el rastreo entra a “Mis pedidos”. Los estados de la demo son procesando, enviado y entregado.';
    else if(/devol|retorno/.test(q))a='En “Mis pedidos” abre “Solicitar devolución”, selecciona un motivo y registra el detalle.';
    else if(/pago|tarjeta|efectivo|transfer/.test(q))a='La demo ofrece tarjeta, efectivo contra entrega y transferencia. Los datos de tarjeta nunca se guardan en localStorage.';
    else if(/stock|inventario/.test(q))a='El stock se descuenta al confirmar una compra y el panel admin muestra alertas cuando quedan 5 unidades o menos.';
    document.getElementById('chatLog').textContent='NEXORA Assist: '+a;input.value='';
  }

  function openModal(html){document.getElementById('modal').innerHTML=html;document.getElementById('modalBackdrop').classList.add('open')}
  function closeModal(){document.getElementById('modalBackdrop').classList.remove('open');document.getElementById('modal').innerHTML=''}
  let toastTimer; function toast(msg){const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');clearTimeout(toastTimer);toastTimer=setTimeout(()=>t.classList.remove('show'),2600)}
  function seedDemoAgain(){if(!confirm('Esto restaurará productos, usuarios, pedidos y transacciones de ejemplo. ¿Continuar?'))return;localStorage.removeItem(DBKEY);location.reload()}

  function init(){
    ensureCSRF();renderCartBadge();renderFilters();renderProducts();renderAccount();renderOrders();
    document.querySelector('[data-view="store"]').classList.add('active');
  }

  return {
    showView,renderProducts,productDetails,addToCart,updateQty,removeCart,openCart,closeCart,applyCoupon,checkout,
    togglePayment,submitOrder,renderOrders,advanceOrder,openReturn,submitReturn,renderAccount,openLogin,login,logout,openRegister,register,
    openRecovery,recovery,editProfile,saveProfile,renderAdmin,openProductEditor,saveProduct,deleteProduct,downloadInvoice,downloadReport,
    submitSupport,chat,openModal,closeModal,seedDemoAgain
  };
})();

window.App=App;
App.showView('store');
</script>
</body>
</html>
