<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Menú de Pizzas · Viajeros Bakery</title>
  <style>
    :root { --bg:#0b0f19; --card:#121a2b; --text:#e9eefc; --muted:#a8b3d6; --accent:#6ea8ff; }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial;
      background:linear-gradient(180deg,#070a12, var(--bg));
      color:var(--text)
    }
    header{padding:32px 18px;max-width:1000px;margin:auto}
    h1{margin:0 0 8px;font-size:28px}
    p{margin:0;color:var(--muted)}
    main{max-width:1000px;margin:auto;padding:0 18px 40px}
    .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:14px;margin-top:18px}
    .card{
      background:rgba(18,26,43,.9);
      border:1px solid rgba(255,255,255,.08);
      border-radius:16px;
      padding:16px;
      box-shadow:0 10px 30px rgba(0,0,0,.35)
    }
    .row{display:flex;justify-content:space-between;gap:10px;align-items:flex-start}
    .name{font-weight:800;font-size:16px}
    .tag{
      display:inline-block;
      margin-top:10px;
      font-size:12px;
      padding:6px 10px;
      border-radius:999px;
      background:rgba(110,168,255,.12);
      border:1px solid rgba(110,168,255,.35);
      color:#cfe0ff
    }
    .desc{margin-top:8px;color:var(--muted);font-size:14px;line-height:1.35}

    /* Lista de tamaños/precios */
    .sizes{
      margin:12px 0 0;
      padding:0;
      list-style:none;
      border-top:1px solid rgba(255,255,255,.08);
    }
    .sizes li{
      display:flex;
      justify-content:space-between;
      gap:12px;
      padding:10px 0;
      border-bottom:1px solid rgba(255,255,255,.06);
      font-size:14px;
      color:var(--text);
    }
    .sizes .size{color:var(--muted)}
    .sizes .price{font-weight:800;color:var(--accent);white-space:nowrap}

    footer{max-width:1000px;margin:auto;padding:0 18px 30px;color:var(--muted);font-size:13px}
    .phones{margin-top:8px}
    .phones strong{color:var(--text)}
  </style>
</head>
<body>
  <header>
    <h1>Menú de Pizzas</h1>
    <p>Actualizado: <span id="fecha"></span> · Ordena por WhatsApp / Teléfono</p>
  </header>

  <main>
    <div class="grid">

      <!-- Pizza de Queso -->
      <div class="card">
        <div class="row">
          <div class="name">Pizza de Queso</div>
        </div>
        <div class="desc">Mozzarella full y salsa tradicional.</div>
        <ul class="sizes">
          <li><span class="size">8"</span>  <span class="price">$5.99</span></li>
          <li><span class="size">10"</span> <span class="price">$8.99</span></li>
          <li><span class="size">12"</span> <span class="price">$12.99</span></li>
          <li><span class="size">16"</span> <span class="price">$17.99</span></li>
        </ul>
        <div class="tag">Clásica</div>
      </div>

      <!-- Pizza de Pepperoni -->
      <div class="card">
        <div class="row">
          <div class="name">Pizza de Pepperoni</div>
        </div>
        <div class="desc">Salsa, queso mozzarella y pepperoni.</div>
        <ul class="sizes">
          <li><span class="size">8"</span>  <span class="price">$7.99</span></li>
          <li><span class="size">10"</span> <span class="price">$10.99</span></li>
          <li><span class="size">12"</span> <span class="price">$13.99</span></li>
          <li><span class="size">16"</span> <span class="price">$21.99</span></li>
        </ul>
        <div class="tag">Favorita</div>
      </div>

      <!-- Pizza de Vegetales -->
      <div class="card">
        <div class="row">
          <div class="name">Pizza de Vegetales</div>
        </div>
        <div class="desc">Vegetales frescos y extra queso.</div>
        <ul class="sizes">
          <li><span class="size">8"</span>  <span class="price">$8.99</span></li>
          <li><span class="size">10"</span> <span class="price">$11.99</span></li>
          <li><span class="size">12"</span> <span class="price">$14.99</span></li>
          <li><span class="size">16"</span> <span class="price">$19.99</span></li>
        </ul>
        <div class="tag">Veggie</div>
      </div>

      <!-- Pizza 3 Carnes -->
      <div class="card">
        <div class="row">
          <div class="name">Pizza 3 Carnes</div>
        </div>
        <div class="desc">Bacon, chorizo, pepperoni y salchicha.</div>
        <ul class="sizes">
          <li><span class="size">8"</span>  <span class="price">$11.99</span></li>
          <li><span class="size">10"</span> <span class="price">$14.99</span></li>
          <li><span class="size">12"</span> <span class="price">$17.99</span></li>
          <li><span class="size">16"</span> <span class="price">$25.99</span></li>
        </ul>
        <div class="tag">Carnívora</div>
      </div>

    </div>
  </main>

  <footer>
    <div>📍 Dirección: (ponla aquí) · ⏰ Horario: (ponlo aquí)</div>
    <div class="phones">📞 <strong>Llama al:</strong> 787-260-2181 · 787-837-7228 · 787-698-7228</div>
    <div>💬 WhatsApp: (ponlo aquí si es uno de esos números o otro)</div>
  </footer>

  <script>
    const d = new Date();
    const opciones = { year: 'numeric', month: 'long', day: 'numeric' };
    document.getElementById('fecha').textContent = d.toLocaleDateString('es-PR', opciones);
  </script>
</body>
</html>

    const f = new Date();
    document.getElementById("fecha").textContent =
      f.toLocaleDateString("es-PR", { year:"numeric", month:"long", day:"numeric" });
  </script>
</body>
</html>
