<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Pizza Price List · Viajeros Bakery</title>
  <style>
    :root{
      --bg:#d7cfb4;         /* tono parecido al flyer */
      --ink:#111;
      --muted:#3a3a3a;
      --paper:#f3ead6;      /* tarjetas beige */
      --paper2:#efe3c8;
      --shadow:0 18px 45px rgba(0,0,0,.25);
      --shadow2:0 14px 28px rgba(0,0,0,.18);
      --radius:18px;
      --accent:#b31b1b;     /* rojo */
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      color:var(--ink);
      background:
        radial-gradient(1000px 650px at 20% -10%, rgba(255,255,255,.45), rgba(255,255,255,0)),
        linear-gradient(180deg, rgba(255,255,255,.25), rgba(255,255,255,0)),
        url("assets/bg-doodles.png"); /* pon aquí tu fondo */
      background-size: cover;
      background-position: center;
      min-height:100vh;
    }

    .wrap{
      max-width:1100px;
      margin:0 auto;
      padding:22px 16px 28px;
    }

    /* Header */
    .top{
      display:flex;
      align-items:flex-start;
      justify-content:space-between;
      gap:16px;
      margin-bottom:14px;
    }
    .titleBlock{
      display:flex;
      flex-direction:column;
      gap:6px;
    }
    .title{
      margin:0;
      font-size:64px;
      line-height:0.95;
      letter-spacing:1px;
      font-weight:900;
      color:var(--accent);
      text-transform:uppercase;
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
      filter: drop-shadow(0 10px 12px rgba(0,0,0,.25));
    }

    /* Layout principal */
    .layout{
      display:grid;
      grid-template-columns: 1.05fr .95fr;
      gap:18px;
      align-items:start;
      margin-top:10px;
    }

    /* Tarjetas izquierda */
    .menuCol{
      display:flex;
      flex-direction:column;
      gap:14px;
    }
    .card{
      background: linear-gradient(180deg, var(--paper), var(--paper2));
      border-radius: var(--radius);
      box-shadow: var(--shadow2);
      padding:16px 16px 14px;
      border: 1px solid rgba(0,0,0,.06);
    }
    .card h3{
      margin:0 0 10px;
      font-size:30px;
      font-weight:900;
      font-family: Georgia, "Times New Roman", serif;
    }
    .smallNote{
      margin:-6px 0 10px;
      color:var(--muted);
      font-size:13px;
      font-weight:600;
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
    }
    .prices .size{
      font-family: Georgia, "Times New Roman", serif;
      font-weight:900;
    }

    /* Fotos derecha tipo polaroid */
    .photosCol{
      display:flex;
      flex-direction:column;
      gap:14px;
      padding-top:6px;
    }
    .polaroid{
      background:#fff;
      border-radius:14px;
      padding:12px 12px 18px;
      box-shadow: var(--shadow);
      border:1px solid rgba(0,0,0,.08);
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
    }

    /* Barra inferior “LLAMA AL” */
    .callout{
      margin-top:18px;
      background: rgba(255,255,255,.55);
      border: 1px solid rgba(0,0,0,.08);
      border-radius: 22px;
      padding:18px 16px;
      display:flex;
      align-items:center;
      justify-content:center;
      gap:14px;
      box-shadow: var(--shadow2);
      backdrop-filter: blur(6px);
    }
    .phoneIcon{
      width:62px;
      height:62px;
      border-radius:999px;
      background: var(--accent);
      display:grid;
      place-items:center;
      box-shadow: 0 14px 26px rgba(179,27,27,.35);
      flex:0 0 auto;
    }
    .phoneIcon svg{ width:34px; height:34px; fill:#fff; }
    .callText{
      text-align:center;
      line-height:1.15;
    }
    .callText .label{
      font-weight:1000;
      letter-spacing:1px;
      font-size:22px;
      text-transform:uppercase;
    }
    .callText .nums{
      margin-top:6px;
      font-size:22px;
      font-weight:1000;
    }

    /* Responsive */
    @media (max-width: 900px){
      .title{font-size:52px}
      .subtitle{font-size:32px}
      .layout{grid-template-columns: 1fr; }
      .photosCol{ order:2; }
      .polaroid img{ height:210px; }
    }
    @media (max-width: 520px){
      .top{align-items:center}
      .logo{width:130px}
      .title{font-size:44px}
      .subtitle{font-size:28px}
      .card h3{font-size:26px}
      .prices li{font-size:17px}
      .callText .nums{font-size:18px}
    }
  </style>
</head>

<body>
  <div class="wrap">

    <header class="top">
      <div class="titleBlock">
        <h1 class="title">PIZZA</h1>
        <p class="subtitle">Price List</p>
      </div>

      <!-- Logo -->
      <img class="logo" src="assets/logo.png" alt="Viajeros Bakery" />
    </header>

    <main class="layout">

      <!-- Izquierda: menú -->
      <section class="menuCol">

        <article class="card">
          <h3>Pizza de Queso</h3>
          <ul class="prices">
            <li><span class="size">Pizza de 8"</span>  <span>$5.99</span></li>
            <li><span class="size">Pizza de 10"</span> <span>$8.99</span></li>
            <li><span class="size">Pizza de 12"</span> <span>$12.99</span></li>
            <li><span class="size">Pizza de 16"</span> <span>$17.99</span></li>
          </ul>
        </article>

        <article class="card">
          <h3>Pizza de Pepperoni</h3>
          <ul class="prices">
            <li><span class="size">Pizza de 8"</span>  <span>$7.99</span></li>
            <li><span class="size">Pizza de 10"</span> <span>$10.99</span></li>
            <li><span class="size">Pizza de 12"</span> <span>$13.99</span></li>
            <li><span class="size">Pizza de 16"</span> <span>$21.99</span></li>
          </ul>
        </article>

        <article class="card">
          <h3>Pizza de Vegetales</h3>
          <ul class="prices">
            <li><span class="size">Pizza de 8"</span>  <span>$8.99</span></li>
            <li><span class="size">Pizza de 10"</span> <span>$11.99</span></li>
            <li><span class="size">Pizza de 12"</span> <span>$14.99</span></li>
            <li><span class="size">Pizza de 16"</span> <span>$19.99</span></li>
          </ul>
        </article>

        <article class="card">
          <h3>Pizza 3 Carnes</h3>
          <p class="smallNote">Bacon, Chorizo, Pepperoni, Salchicha</p>
          <ul class="prices">
            <li><span class="size">Pizza de 8"</span>  <span>$11.99</span></li>
            <li><span class="size">Pizza de 10"</span> <span>$14.99</span></li>
            <li><span class="size">Pizza de 12"</span> <span>$17.99</span></li>
            <li><span class="size">Pizza de 16"</span> <span>$25.99</span></li>
          </ul>
        </article>

      </section>

      <!-- Derecha: fotos -->
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
        <div class="nums">787-260-2181 · 787-837-7228 · 787-698-7228</div>
      </div>
    </footer>

  </div>
</body>
</html>
