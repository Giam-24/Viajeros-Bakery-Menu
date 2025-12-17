# Viajeros-Bakery-Menu
<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Menú de Pizzas</title>
  <style>
    :root { --bg:#0b0f19; --card:#121a2b; --text:#e9eefc; --muted:#a8b3d6; --accent:#6ea8ff; }
    *{box-sizing:border-box} body{margin:0;font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial;background:linear-gradient(180deg,#070a12, var(--bg));color:var(--text)}
    header{padding:32px 18px;max-width:1000px;margin:auto}
    h1{margin:0 0 8px;font-size:28px} p{margin:0;color:var(--muted)}
    main{max-width:1000px;margin:auto;padding:0 18px 40px}
    .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:14px;margin-top:18px}
    .card{background:rgba(18,26,43,.9);border:1px solid rgba(255,255,255,.08);border-radius:16px;padding:16px;box-shadow:0 10px 30px rgba(0,0,0,.35)}
    .row{display:flex;justify-content:space-between;gap:10px;align-items:flex-start}
    .name{font-weight:700}
    .price{font-weight:800;color:var(--accent);white-space:nowrap}
    .desc{margin-top:8px;color:var(--muted);font-size:14px;line-height:1.35}
    .tag{display:inline-block;margin-top:10px;font-size:12px;padding:6px 10px;border-radius:999px;background:rgba(110,168,255,.12);border:1px solid rgba(110,168,255,.35);color:#cfe0ff}
    footer{max-width:1000px;margin:auto;padding:0 18px 30px;color:var(--muted);font-size:13px}
  </style>
</head>
<body>
  <header>
    <h1>Menú de Pizzas</h1>
    <p>Actualizado: <span id="fecha"></span> · Ordena por WhatsApp / Teléfono</p>
  </header>

  <main>
    <div class="grid">
      <div class="card">
        <div class="row">
          <div class="name">Pepperoni</div>
          <div class="price">$12.99</div>
        </div>
        <div class="desc">Salsa, queso mozzarella y pepperoni.</div>
        <div class="tag">Clásica</div>
      </div>

      <div class="card">
        <div class="row">
          <div class="name">Suprema</div>
          <div class="price">$14.99</div>
        </div>
        <div class="desc">Pepperoni, jamón, pimientos, cebolla y aceitunas.</div>
        <div class="tag">Más vendida</div>
      </div>

      <div class="card">
        <div class="row">
          <div class="name">Hawaiana</div>
          <div class="price">$13.99</div>
        </div>
        <div class="desc">Jamón y piña con extra queso.</div>
        <div class="tag">Dulce & salada</div>
      </div>

      <div class="card">
        <div class="row">
          <div class="name">Queso</div>
          <div class="price">$10.99</div>
        </div>
        <div class="desc">Mozzarella full, salsa tradicional.</div>
        <div class="tag">Kids friendly</div>
      </div>
    </div>
  </main>

  <footer>
    <div>📍 Dirección: (ponla aquí) · ⏰ Horario: (ponlo aquí)</div>
    <div>📞 Tel: (xxx) xxx-xxxx · 💬 WhatsApp: (xxx) xxx-xxxx</div>
  </footer>

  <script>
    const f = new Date();
    document.getElementById("fecha").textContent =
      f.toLocaleDateString("es-PR", { year:"numeric", month:"long", day:"numeric" });
  </script>
</body>
</html>
