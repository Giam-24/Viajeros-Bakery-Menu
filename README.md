<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Menú · Viajeros Bakery</title>

  <style>
    :root{
      /* Blancos, rojos y grises (sin azules) */
      --bg:#f2f2f2;
      --ink:#111111;
      --muted:#4a4a4a;

      --paper:#ffffff;
      --paper2:#f7f7f7;
      --line:rgba(0,0,0,.10);

      --shadow:0 18px 45px rgba(0,0,0,.18);
      --shadow2:0 14px 28px rgba(0,0,0,.14);

      --radius:18px;

      --red:#b10f0f;
      --red2:#e01616;
    }

    *{box-sizing:border-box}

    body{
      margin:0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      color:var(--ink);
      background:
        radial-gradient(1000px 650px at 20% -10%, rgba(255,255,255,.95), rgba(255,255,255,0)),
        linear-gradient(180deg, #ffffff, var(--bg)),
        url("assets/bg-doodles.png");
      background-size: cover;
      background-position: center;
      min-height:100vh;
    }

    /* Mantener “flyer” junto en vertical: NO baja la columna de fotos */
    .viewport{
      display:flex;
      justify-content:center;
      padding:22px 10px 28px;
      overflow:hidden;
    }
    .page{
      width:1100px;
      transform-origin: top center;
    }

    /* NAV */
    .nav{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      padding:0 6px 10px;
    }
    .navLinks{ display:flex; gap:10px; flex-wrap:wrap; }
    .navBtn{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding:10px 12px;
      border-radius:14px;
      border:1px solid rgba(0,0,0,.12);
      background: rgba(255,255,255,.82);
      box-shadow: var(--shadow2);
      text-decoration:none;
      color:var(--ink);
      font-weight:900;
      cursor:pointer;
      user-select:none;
    }
    .navBtn:hover{ transform: translateY(-1px); }
    .navBtn[aria-current="page"]{
      background: linear-gradient(180deg, var(--red2), var(--red));
      color:#fff;
      border:1px solid rgba(0,0,0,.10);
    }

    /* HEADER */
    .top{
      display:flex;
      align-items:flex-start;
      justify-content:space-between;
      gap:16px;
      margin-bottom:14px;
      padding:0 6px;
    }
    .titleBlock{ display:flex; flex-direction:column; gap:6px; }
    .title{
      margin:0;
      font-size:64px;
      line-height:0.95;
      letter-spacing:1px;
      font-weight:900;
      color:var(--red);
      text-transform:uppercase;
      text-shadow: 0 10px 18px rgba(0,0,0,.10);
    }
    .subtitle{
      margin:0;
      font-size:38px;
      font-weight:900;
      color:var(--ink);
      font-family: Georgia, "Times New Roman", serif;
    }
    .logo{
      width:165px;
      height:auto;
      filter: drop-shadow(0 10px 12px rgba(0,0,0,.18));
    }

    /* LAYOUT: siempre 2 columnas */
    .layout{
      display:grid;
      grid-template-columns: 1.05fr .95fr;
      gap:18px;
      align-items:start;
      margin-top:10px;
      padding:0 6px;
    }

    /* CARDS */
    .menuCol{ display:flex; flex-direction:column; gap:14px; }
    .card{
      background: linear-gradient(180deg, var(--paper), var(--paper2));
      border-radius: var(--radius);
      box-shadow: var(--shadow2);
      padding:16px 16px 14px;
      border: 1px solid var(--line);
    }
    .card h3{
      margin:0 0 10px;
      font-size:30px;
      font-weight:900;
      font-family: Georgia, "Times New Roman", serif;
      position:relative;
      padding-bottom:8px;
    }
    .card h3::after{
      content:"";
      position:absolute;
      left:0;
      bottom:0;
      width:78px;
      height:4px;
      border-radius:999px;
      background: linear-gradient(90deg, var(--red2), var(--red));
      opacity:.95;
    }
    .smallNote{
      margin:-6px 0 10px;
      color:var(--muted);
      font-size:13px;
      font-weight:650;
    }

    .prices{
      display:grid;
      gap:8px;
      margin:0;
      padding:0;
      list-style:none;
    }
    .prices li{
      display:flex;
      justify-content:space-between;
      gap:10px;
      font-size:18px;
      font-weight:800;
      border-bottom: 1px dashed rgba(0,0,0,.14);
      padding-bottom:6px;
    }
    .prices li:last-child{ border-bottom:none; padding-bottom:0; }
    .prices .size{
      font-family: Georgia, "Times New Roman", serif;
      font-weight:900;
      color:#222;
    }
    .prices .val{
      font-weight:1000;
      color:var(--red);
      white-space:nowrap;
    }

    /* POLAROIDS */
    .photosCol{ display:flex; flex-direction:column; gap:14px; padding-top:6px; }
    .polaroid{
      background:#ffffff;
      border-radius:14px;
      padding:12px 12px 18px;
      box-shadow: var(--shadow);
      border:1px solid rgba(0,0,0,.10);
      transform: rotate(-1.2deg);
    }
    .polaroid:nth-child(2){ transform: rotate(1.1deg); }
    .polaroid:nth-child(3){ transform: rotate(-0.8deg); }
    .polaroid:nth-child(4){ transform: rotate(1.4deg); }
    .polaroid img{
      width:100%;
      height:180px;
      object-fit:cover;
      border-radius:10px;
      display:block;
      filter: contrast(1.03) saturate(1.02);
    }

    /* CALLOUT */
    .callout{
      margin-top:18px;
      background: rgba(255,255,255,.82);
      border: 1px solid rgba(0,0,0,.10);
      border-radius: 22px;
      padding:18px 16px;
      display:flex;
      align-items:center;
      justify-content:center;
      gap:14px;
      box-shadow: var(--shadow2);
      backdrop-filter: blur(6px);
      margin-left:6px;
      margin-right:6px;
    }
    .phoneIcon{
      width:62px;
      height:62px;
      border-radius:999px;
      background: linear-gradient(180deg, var(--red2), var(--red));
      display:grid;
      place-items:center;
      box-shadow: 0 14px 26px rgba(177,15,15,.25);
      flex:0 0 auto;
      border:1px solid rgba(0,0,0,.10);
    }
    .phoneIcon svg{ width:34px; height:34px; fill:#fff; }
    .callText{ text-align:center; line-height:1.15; }
    .callText .label{
      font-weight:1000;
      letter-spacing:1px;
      font-size:22px;
      text-transform:uppercase;
      color:#111;
    }
    .callText .nums{
      margin-top:6px;
      font-size:22px;
      font-weight:1000;
      color:#111;
    }
    .callText .nums span{ color:var(--red); }

    /* HOME BOX */
    .homeBox{
      margin:12px 6px 0;
      background: rgba(255,255,255,.86);
      border:1px solid rgba(0,0,0,.10);
      border-radius:22px;
      padding:22px;
      box-shadow: var(--shadow2);
    }
    .homeTitle{ margin:0 0 6px; font-size:34px; font-weight:1000; }
    .homeText{ margin:0 0 16px; color:var(--muted); font-weight:650; }
    .homeActions{ display:flex; gap:12px; flex-wrap:wrap; }
    .bigBtn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:10px;
      padding:14px 16px;
      border-radius:18px;
      border:1px solid rgba(0,0,0,.12);
      background: linear-gradient(180deg, #fff, #f6f6f6);
      box-shadow: var(--shadow2);
      text-decoration:none;
      color:var(--ink);
      font-weight:1000;
      font-size:18px;
      cursor:pointer;
    }
    .bigBtn.primary{
      background: linear-gradient(180deg, var(--red2), var(--red));
      color:#fff;
      border:1px solid rgba(0,0,0,.10);
    }
    .bigBtn:hover{ transform: translateY(-1px); }

    /* Vistas */
    .view{ display:none; }
    .view.is-active{ display:block; }

    /* ESCALA para móvil: mantiene TODO junto */
    @media (max-width: 1100px){ .page{ transform: scale(.95); } }
    @media (max-width: 1040px){ .page{ transform: scale(.90); } }
    @media (max-width: 980px) { .page{ transform: scale(.85); } }
    @media (max-width: 920px) { .page{ transform: scale(.80); } }
    @media (max-width: 860px) { .page{ transform: scale(.75); } }
    @media (max-width: 800px) { .page{ transform: scale(.70); } }
    @media (max-width: 740px) { .page{ transform: scale(.66); } }
    @media (max-width: 690px) { .page{ transform: scale(.62); } }
  </style>
</head>

<body>
  <div class="viewport">
    <div class="page">

      <!-- NAV (cambia vistas) -->
      <div class="nav">
        <button class="navBtn" data-view="home" aria-current="page">🏠 Inicio</button>
        <div class="navLinks">
          <button class="navBtn" data-view="pizzas">🍕 Pizzas</button>
          <button class="navBtn" data-view="sandwiches">🥪 Sándwiches</button>
        </div>
      </div>

      <!-- ========== HOME ========== -->
      <section id="home" class="view is-active">
        <header class="top">
          <div class="titleBlock">
            <h1 class="title">MENÚ</h1>
            <p class="subtitle">Viajeros Bakery</p>
          </div>
          <img class="logo" src="assets/logo.png" alt="Viajeros Bakery" />
        </header>

        <section class="homeBox">
          <h2 class="homeTitle">Selecciona una categoría</h2>
          <p class="homeText">Entra al menú que quieras con un solo click.</p>

          <div class="homeActions">
            <button class="bigBtn primary" data-view="pizzas">🍕 Ver Menú de Pizzas</button>
            <button class="bigBtn" data-view="sandwiches">🥪 Ver Menú de Sándwiches</button>
          </div>
        </section>

        <footer class="callout">
          <div class="phoneIcon" aria-hidden="true">
            <svg viewBox="0 0 24 24">
              <path d="M6.62 10.79a15.05 15.05 0 0 0 6.59 6.59l2.2-2.2a1 1 0 0 1 1.01-.24c1.12.37 2.33.57 3.58.57a1 1 0 0 1 1 1V20a1 1 0 0 1-1 1C10.07 21 3 13.93 3 5a1 1 0 0 1 1-1h3.5a1 1 0 0 1 1 1c0 1.25.2 2.46.57 3.58a1 1 0 0 1-.25 1.01l-2.2 2.2z"/>
            </svg>
          </div>
          <div class="callText">
            <div class="label">LLAMA AL:</div>
            <div class="nums">
              <span>787-260-2181</span> · <span>787-837-7228</span> · <span>787-698-7228</span>
            </div>
          </div>
        </footer>
      </section>

      <!-- ========== PIZZAS ========== -->
      <section id="pizzas" class="view">
        <header class="top">
          <div class="titleBlock">
            <h1 class="title">PIZZA</h1>
            <p class="subtitle">Price List</p>
          </div>
          <img class="logo" src="assets/logo.png" alt="Viajeros Bakery" />
        </header>

        <main class="layout">
          <section class="menuCol">

            <article class="card">
              <h3>Pizza de Queso</h3>
              <ul class="prices">
                <li><span class="size">Pizza de 8"</span>  <span class="val">$5.99</span></li>
                <li><span class="size">Pizza de 10"</span> <span class="val">$8.99</span></li>
                <li><span class="size">Pizza de 12"</span> <span class="val">$12.99</span></li>
                <li><span class="size">Pizza de 16"</span> <span class="val">$17.99</span></li>
              </ul>
            </article>

            <article class="card">
              <h3>Pizza de Pepperoni</h3>
              <ul class="prices">
                <li><span class="size">Pizza de 8"</span>  <span class="val">$7.99</span></li>
                <li><span class="size">Pizza de 10"</span> <span class="val">$10.99</span></li>
                <li><span class="size">Pizza de 12"</span> <span class="val">$13.99</span></li>
                <li><span class="size">Pizza de 16"</span> <span class="val">$21.99</span></li>
              </ul>
            </article>

            <article class="card">
              <h3>Pizza de Vegetales</h3>
              <ul class="prices">
                <li><span class="size">Pizza de 8"</span>  <span class="val">$8.99</span></li>
                <li><span class="size">Pizza de 10"</span> <span class="val">$11.99</span></li>
                <li><span class="size">Pizza de 12"</span> <span class="val">$14.99</span></li>
                <li><span class="size">Pizza de 16"</span> <span class="val">$19.99</span></li>
              </ul>
            </article>

            <article class="card">
              <h3>Pizza 3 Carnes</h3>
              <p class="smallNote">Bacon, Chorizo, Pepperoni, Salchicha</p>
              <ul class="prices">
                <li><span class="size">Pizza de 8"</span>  <span class="val">$11.99</span></li>
                <li><span class="size">Pizza de 10"</span> <span class="val">$14.99</span></li>
                <li><span class="size">Pizza de 12"</span> <span class="val">$17.99</span></li>
                <li><span class="size">Pizza de 16"</span> <span class="val">$25.99</span></li>
              </ul>
            </article>

          </section>

          <aside class="photosCol">
            <div class="polaroid"><img src="assets/pizza-1.jpg" alt="Pizza" /></div>
            <div class="polaroid"><img src="assets/pizza-2.jpg" alt="Pizza" /></div>
            <div class="polaroid"><img src="assets/pizza-3.jpg" alt="Pizza" /></div>
            <div class="polaroid"><img src="assets/pizza-4.jpg" alt="Pizza" /></div>
          </aside>
        </main>

        <footer class="callout">
          <div class="phoneIcon" aria-hidden="true">
            <svg viewBox="0 0 24 24">
              <path d="M6.62 10.79a15.05 15.05 0 0 0 6.59 6.59l2.2-2.2a1 1 0 0 1 1.01-.24c1.12.37 2.33.57 3.58.57a1 1 0 0 1 1 1V20a1 1 0 0 1-1 1C10.07 21 3 13.93 3 5a1 1 0 0 1 1-1h3.5a1 1 0 0 1 1 1c0 1.25.2 2.46.57 3.58a1 1 0 0 1-.25 1.01l-2.2 2.2z"/>
            </svg>
          </div>
          <div class="callText">
            <div class="label">LLAMA AL:</div>
            <div class="nums">
              <span>787-260-2181</span> · <span>787-837-7228</span> · <span>787-698-7228</span>
            </div>
          </div>
        </footer>
      </section>

      <!-- ========== SÁNDWICHES (placeholder) ========== -->
      <section id="sandwiches" class="view">
        <header class="top">
          <div class="titleBlock">
            <h1 class="title">SÁNDWICHES</h1>
            <p class="subtitle">Price List</p>
          </div>
          <img class="logo" src="assets/logo.png" alt="Viajeros Bakery" />
        </header>

        <main class="layout">
          <section class="menuCol">

            <article class="card">
              <h3>Próximamente</h3>
              <p class="smallNote">Cuando tengas el menú de sándwiches, lo rellenamos aquí.</p>
              <ul class="prices">
                <li><span class="size">Regular</span> <span class="val">—</span></li>
                <li><span class="size">Combo</span>   <span class="val">—</span></li>
              </ul>
            </article>

            <article class="card">
              <h3>Ejemplo</h3>
              <p class="smallNote">Reemplaza esta tarjeta cuando tengas la info real.</p>
              <ul class="prices">
                <li><span class="size">Regular</span> <span class="val">$0.00</span></li>
                <li><span class="size">Combo</span>   <span class="val">$0.00</span></li>
              </ul>
            </article>

          </section>

          <aside class="photosCol">
            <div class="polaroid"><img src="assets/sandwich-1.jpg" alt="Sándwich" /></div>
            <div class="polaroid"><img src="assets/sandwich-2.jpg" alt="Sándwich" /></div>
            <div class="polaroid"><img src="assets/sandwich-3.jpg" alt="Sándwich" /></div>
            <div class="polaroid"><img src="assets/sandwich-4.jpg" alt="Sándwich" /></div>
          </aside>
        </main>

        <footer class="callout">
          <div class="phoneIcon" aria-hidden="true">
            <svg viewBox="0 0 24 24">
              <path d="M6.62 10.79a15.05 15.05 0 0 0 6.59 6.59l2.2-2.2a1 1 0 0 1 1.01-.24c1.12.37 2.33.57 3.58.57a1 1 0 0 1 1 1V20a1 1 0 0 1-1 1C10.07 21 3 13.93 3 5a1 1 0 0 1 1-1h3.5a1 1 0 0 1 1 1c0 1.25.2 2.46.57 3.58a1 1 0 0 1-.25 1.01l-2.2 2.2z"/>
            </svg>
          </div>
          <div class="callText">
            <div class="label">LLAMA AL:</div>
            <div class="nums">
              <span>787-260-2181</span> · <span>787-837-7228</span> · <span>787-698-7228</span>
            </div>
          </div>
        </footer>
      </section>

    </div>
  </div>

  <script>
    function setView(viewId){
      document.querySelectorAll('.view').forEach(v => v.classList.remove('is-active'));
      const el = document.getElementById(viewId);
      if (el) el.classList.add('is-active');

      document.querySelectorAll('[data-view]').forEach(b => {
        if (b.getAttribute('data-view') === viewId) b.setAttribute('aria-current','page');
        else b.removeAttribute('aria-current');
      });

      // opcional: guarda la vista para que vuelva ahí al recargar
      try{ localStorage.setItem('viajeros_view', viewId); }catch(e){}
    }

    // Clicks en botones
    document.addEventListener('click', (e) => {
      const btn = e.target.closest('[data-view]');
      if (!btn) return;
      e.preventDefault();
      setView(btn.getAttribute('data-view'));
    });

    // Al cargar: vuelve a la última vista
    (function init(){
      let saved = null;
      try{ saved = localStorage.getItem('viajeros_view'); }catch(e){}
      setView(saved || 'home');
    })();
  </script>
</body>
</html>
