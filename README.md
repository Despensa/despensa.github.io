DESPENSA
<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ZeroZero — Menu</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Jost:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream:    #f7f2ea;
    --warm:     #faf6f0;
    --charcoal: #1e1a14;
    --brown:    #5c3d1e;
    --rust:     #b5471b;
    --gold:     #c9973a;
    --muted:    #8a7560;
    --border:   #e2d8c8;
    --tag-veg:  #3a6b3a;
    --tag-gf:   #7a4a1e;
    --tag-hot:  #b5471b;
  }

  *, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--warm);
    color: var(--charcoal);
    font-family: 'Jost', sans-serif;
    font-weight: 300;
    min-height: 100vh;
  }

  /* Grain texture */
  body::after {
    content:'';
    position:fixed;
    inset:0;
    pointer-events:none;
    z-index:999;
    opacity:.025;
    background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='200' height='200' filter='url(%23n)'/%3E%3C/svg%3E");
  }

  /* ─── HERO ─────────────────────────────────────────────── */
  .hero {
    text-align: center;
    padding: 80px 24px 60px;
    border-bottom: 1px solid var(--border);
    position: relative;
  }
  .hero::before {
    content:'';
    position:absolute;
    bottom:0; left:50%; transform:translateX(-50%);
    width:1px; height:40px;
    background: linear-gradient(to bottom, var(--border), transparent);
  }
  .hero-eyebrow {
    font-family: 'Jost', sans-serif;
    font-size: 10px;
    font-weight: 500;
    letter-spacing: .45em;
    text-transform: uppercase;
    color: var(--rust);
    margin-bottom: 20px;
  }
  .hero h1 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(64px, 14vw, 120px);
    font-weight: 300;
    line-height: .9;
    letter-spacing: -.02em;
    color: var(--charcoal);
  }
  .hero h1 span { color: var(--rust); font-style: italic; }
  .hero-sub {
    margin-top: 20px;
    font-size: 13px;
    font-weight: 300;
    letter-spacing: .12em;
    color: var(--muted);
    text-transform: uppercase;
  }
  .hero-rule {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 18px;
    margin-top: 32px;
  }
  .hero-rule::before, .hero-rule::after {
    content:'';
    width:80px; height:1px;
    background: linear-gradient(to right, transparent, var(--gold));
  }
  .hero-rule::after { background: linear-gradient(to left, transparent, var(--gold)); }
  .hero-rule span { color: var(--gold); font-size:14px; }

  /* ─── NAV TABS ──────────────────────────────────────────── */
  .nav-wrap {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(250,246,240,.95);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid var(--border);
  }
  .nav {
    display: flex;
    overflow-x: auto;
    scrollbar-width: none;
    max-width: 900px;
    margin: 0 auto;
    padding: 0 24px;
  }
  .nav::-webkit-scrollbar { display:none; }
  .nav a {
    flex-shrink: 0;
    padding: 16px 20px;
    font-size: 10px;
    font-weight: 500;
    letter-spacing: .3em;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    border-bottom: 2px solid transparent;
    transition: color .2s, border-color .2s;
    white-space: nowrap;
  }
  .nav a:hover { color: var(--charcoal); border-color: var(--rust); }

  /* ─── MAIN LAYOUT ───────────────────────────────────────── */
  .page { max-width: 900px; margin: 0 auto; padding: 0 24px 100px; }

  /* ─── SECTION ───────────────────────────────────────────── */
  .section {
    padding-top: 72px;
    opacity: 0;
    transform: translateY(24px);
    animation: fadeUp .7s forwards;
  }
  .section:nth-child(1)  { animation-delay:.05s }
  .section:nth-child(2)  { animation-delay:.12s }
  .section:nth-child(3)  { animation-delay:.19s }
  .section:nth-child(4)  { animation-delay:.26s }
  .section:nth-child(5)  { animation-delay:.33s }
  .section:nth-child(6)  { animation-delay:.40s }
  .section:nth-child(7)  { animation-delay:.47s }

  @keyframes fadeUp {
    to { opacity:1; transform:translateY(0); }
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-bottom: 32px;
  }
  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 32px;
    font-weight: 300;
    font-style: italic;
    color: var(--charcoal);
    white-space: nowrap;
  }
  .section-line {
    flex:1;
    height:1px;
    background: var(--border);
  }

  /* ─── MENU ITEM ─────────────────────────────────────────── */
  .item {
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: start;
    gap: 16px;
    padding: 20px 0;
    border-bottom: 1px solid var(--border);
    transition: background .15s;
  }
  .item:last-child { border-bottom: none; }

  .item-left { min-width:0; }

  .item-name-row {
    display: flex;
    align-items: baseline;
    gap: 10px;
    flex-wrap: wrap;
  }

  .item-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 20px;
    font-weight: 400;
    color: var(--charcoal);
    line-height: 1.2;
  }

  .video-btn {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    font-family: 'Jost', sans-serif;
    font-size: 10px;
    font-weight: 500;
    letter-spacing: .1em;
    text-transform: uppercase;
    color: var(--gold);
    background: none;
    border: none;
    cursor: pointer;
    padding: 2px 0;
    border-bottom: 1px solid transparent;
    transition: color .2s, border-color .2s;
    flex-shrink: 0;
  }
  .video-btn:hover { color: var(--rust); border-color: var(--rust); }
  .video-btn svg { width:10px; height:10px; fill:currentColor; }

  .item-desc {
    margin-top: 5px;
    font-size: 13px;
    font-weight: 300;
    color: var(--muted);
    line-height: 1.6;
    font-style: italic;
  }

  .item-tags {
    display: flex;
    gap: 6px;
    margin-top: 8px;
    flex-wrap: wrap;
  }
  .tag {
    font-size: 9px;
    font-weight: 500;
    letter-spacing: .12em;
    text-transform: uppercase;
    padding: 2px 7px;
    border-radius: 2px;
    border: 1px solid currentColor;
  }
  .tag-veg  { color: var(--tag-veg); }
  .tag-gf   { color: var(--tag-gf); }
  .tag-hot  { color: var(--tag-hot); }
  .tag-new  { color: var(--gold); }

  .item-price {
    font-family: 'Cormorant Garamond', serif;
    font-size: 19px;
    font-weight: 400;
    color: var(--brown);
    white-space: nowrap;
    padding-top: 2px;
  }

  /* ─── FOOTER ────────────────────────────────────────────── */
  footer {
    text-align: center;
    padding: 40px 24px 60px;
    border-top: 1px solid var(--border);
    font-size: 11px;
    font-weight: 300;
    letter-spacing: .06em;
    color: var(--muted);
    line-height: 2;
    max-width: 900px;
    margin: 0 auto;
  }
  footer span { color: var(--rust); margin: 0 8px; }

  /* ─── VIDEO MODAL ───────────────────────────────────────── */
  .modal {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(15,10,5,.9);
    z-index: 1000;
    align-items: center;
    justify-content: center;
    backdrop-filter: blur(8px);
    opacity: 0;
    transition: opacity .3s ease;
  }
  .modal.active { display: flex; }
  .modal.visible { opacity: 1; }

  .modal-box {
    width: 90%;
    max-width: 860px;
    background: var(--charcoal);
    border-radius: 3px;
    overflow: hidden;
    transform: scale(.94) translateY(16px);
    transition: transform .35s cubic-bezier(.16,1,.3,1);
  }
  .modal.visible .modal-box { transform: scale(1) translateY(0); }

  .modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 14px 20px;
    border-bottom: 1px solid rgba(255,255,255,.07);
  }
  .modal-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 16px;
    font-style: italic;
    font-weight: 300;
    color: var(--cream);
  }
  .modal-close {
    background: none;
    border: none;
    color: var(--muted);
    cursor: pointer;
    line-height: 0;
    padding: 4px;
    transition: color .2s, transform .2s;
  }
  .modal-close:hover { color: #fff; transform: rotate(90deg); }
  .modal-close svg {
    width:18px; height:18px;
    stroke:currentColor;
    fill:none;
    stroke-width:2;
    stroke-linecap:round;
  }

  .video-wrap {
    position: relative;
    padding-bottom: 56.25%;
    background: #000;
  }
  .video-wrap iframe {
    position:absolute; inset:0;
    width:100%; height:100%;
    border:none;
  }
</style>
</head>
<body>

<!-- HERO -->
<header class="hero">
  <p class="hero-eyebrow">Cucina Italiana · Lisboa</p>
  <h1>Zero<span>Zero</span></h1>
  <p class="hero-sub">Ementa · Janeiro 2026</p>
  <div class="hero-rule"><span>✦</span></div>
</header>

<!-- STICKY NAV -->
<nav class="nav-wrap">
  <div class="nav">
    <a href="#antipasti">Antipasti</a>
    <a href="#insalate">Insalate</a>
    <a href="#pasta">Pasta</a>
    <a href="#risotti">Risotti</a>
    <a href="#pizze">Pizze Speciali</a>
    <a href="#calzoni">Calzoni</a>
  </div>
</nav>

<main class="page">

  <!-- ANTIPASTI -->
  <section class="section" id="antipasti">
    <div class="section-header">
      <h2 class="section-title">Antipasti</h2>
      <div class="section-line"></div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row">
          <span class="item-name">Carpaccio di Manzo</span>
          <button class="video-btn" onclick="openVideo('SClk9Ni-xPQ','Carpaccio di Manzo')">
            <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg> ver
          </button>
        </div>
        <p class="item-desc">rúcula, pistácio, queijo pecorino e azeite de trufa</p>
      </div>
      <div class="item-price">16,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row">
          <span class="item-name">Burrata con Prosciutto Crudo di Parma 24 mesi</span>
          <button class="video-btn" onclick="openVideo('dQw4w9WgXcQ','Burrata con Prosciutto')">
            <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg> ver
          </button>
        </div>
        <p class="item-desc">azeite de manjericão</p>
      </div>
      <div class="item-price">19€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row">
          <span class="item-name">Insalata Caprese</span>
        </div>
        <p class="item-desc">mozzarella di bufala Campana DOP, tomate e manjericão</p>
        <div class="item-tags"><span class="tag tag-veg">Vegetariano</span></div>
      </div>
      <div class="item-price">10€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Arancini</span></div>
        <p class="item-desc">arroz siciliano recheado com ragù e ervilhas</p>
      </div>
      <div class="item-price">12€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Frittura di Calamari</span></div>
        <p class="item-desc">mexilhão, pimentos, courgette, beringela, cenoura e brócolos</p>
      </div>
      <div class="item-price">8€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Bruschetta di Verdure & Provola Affumicata</span></div>
        <div class="item-tags"><span class="tag tag-veg">Vegetariano</span></div>
      </div>
      <div class="item-price">16€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Bruschetta Burrata al Prosciutto di Parma 24 mesi</span></div>
      </div>
      <div class="item-price">16€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Tartaro di Tonno e Avocado</span></div>
      </div>
      <div class="item-price">12,5€</div>
    </div>
  </section>

  <!-- INSALATE -->
  <section class="section" id="insalate">
    <div class="section-header">
      <h2 class="section-title">Insalate</h2>
      <div class="section-line"></div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Pera e Gorgonzola</span></div>
        <p class="item-desc">rúcula, nozes e vinagrete de noz</p>
        <div class="item-tags"><span class="tag tag-veg">Vegetariano</span></div>
      </div>
      <div class="item-price">15€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Pancetta e Avocado</span></div>
        <p class="item-desc">frango, coração de alface, Parmigiano Reggiano 22 meses, croutons de alho e vinagrete de mostarda</p>
      </div>
      <div class="item-price">16,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Caesar</span></div>
        <p class="item-desc">coração de alface, Parmigiano Reggiano 22 meses, croutons de alho, speck crocante e molho Caesar</p>
        <div class="item-tags">
          <span class="tag tag-veg" style="cursor:pointer" title="Disponível com frango ou camarão">di Pollo · di Gamberi</span>
        </div>
      </div>
      <div class="item-price">15€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Couscous di Gamberi, Avocado e Legumi</span></div>
      </div>
      <div class="item-price">16,5€</div>
    </div>
  </section>

  <!-- PASTA -->
  <section class="section" id="pasta">
    <div class="section-header">
      <h2 class="section-title">Pasta</h2>
      <div class="section-line"></div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row">
          <span class="item-name">Spaghetti ai Gamberi e Peperoncino</span>
          <button class="video-btn" onclick="openVideo('dQw4w9WgXcQ','Spaghetti ai Gamberi e Peperoncino')">
            <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg> ver
          </button>
        </div>
        <div class="item-tags"><span class="tag tag-hot">Picante</span></div>
      </div>
      <div class="item-price">18,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Spaghetti alla Burrata</span></div>
        <p class="item-desc">molho de tomate e lascas de parmesão</p>
        <div class="item-tags"><span class="tag tag-veg">Vegetariano</span></div>
      </div>
      <div class="item-price">16,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Paccheri al Ragù</span></div>
      </div>
      <div class="item-price">16,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Tagliatelle alla Carbonara</span></div>
        <p class="item-desc">guanciale, queijo Pecorino, gema de ovo BT</p>
      </div>
      <div class="item-price">16,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Pappardelle Verde com Verdure alla Griglia</span></div>
        <p class="item-desc">pesto de tomate seco</p>
        <div class="item-tags"><span class="tag tag-veg">Vegetariano</span></div>
      </div>
      <div class="item-price">17,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row">
          <span class="item-name">Linguini Nero ai Frutti di Mare</span>
          <button class="video-btn" onclick="openVideo('dQw4w9WgXcQ','Linguini Nero ai Frutti di Mare')">
            <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg> ver
          </button>
        </div>
        <div class="item-tags"><span class="tag tag-new">Novità</span></div>
      </div>
      <div class="item-price">21,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Ravioli di Ricotta e Spinaci</span></div>
        <div class="item-tags"><span class="tag tag-veg">Vegetariano</span></div>
      </div>
      <div class="item-price">17€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Ravioli di Vitello e Funghi</span></div>
        <div class="item-tags"><span class="tag tag-new">Novità</span></div>
      </div>
      <div class="item-price">19€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Lasagna al Ragù</span></div>
      </div>
      <div class="item-price">16€</div>
    </div>
  </section>

  <!-- RISOTTI -->
  <section class="section" id="risotti">
    <div class="section-header">
      <h2 class="section-title">Risotti</h2>
      <div class="section-line"></div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row">
          <span class="item-name">Risotto ai Gamberi e Asparagi</span>
          <button class="video-btn" onclick="openVideo('dQw4w9WgXcQ','Risotto ai Gamberi e Asparagi')">
            <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg> ver
          </button>
        </div>
      </div>
      <div class="item-price">18,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Risotto di Speck di Asiago</span></div>
        <p class="item-desc">queijo scamorza fumado e manjerona</p>
      </div>
      <div class="item-price">21€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row">
          <span class="item-name">Risotto Funghi e Tartufo Nero</span>
          <button class="video-btn" onclick="openVideo('dQw4w9WgXcQ','Risotto Funghi e Tartufo Nero')">
            <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg> ver
          </button>
        </div>
        <div class="item-tags"><span class="tag tag-veg">Vegetariano</span></div>
      </div>
      <div class="item-price">21€</div>
    </div>
  </section>

  <!-- PIZZE SPECIALI -->
  <section class="section" id="pizze">
    <div class="section-header">
      <h2 class="section-title">Pizze Speciali</h2>
      <div class="section-line"></div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row">
          <span class="item-name">Burrata</span>
          <button class="video-btn" onclick="openVideo('dQw4w9WgXcQ','Pizza Burrata')">
            <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg> ver
          </button>
        </div>
        <p class="item-desc">tomate, mozzarella fiordilatte, burrata, rúcula e pesto de manjericão</p>
        <div class="item-tags"><span class="tag tag-veg">Vegetariano</span></div>
      </div>
      <div class="item-price">20,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Di Graziano</span></div>
        <p class="item-desc">tomate, mozzarella fiordilatte, ventricina calabrese picante, queijo taleggio e cebola roxa</p>
        <div class="item-tags"><span class="tag tag-hot">Picante</span></div>
      </div>
      <div class="item-price">17,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row">
          <span class="item-name">Tartufi e Porcini</span>
          <button class="video-btn" onclick="openVideo('dQw4w9WgXcQ','Pizza Tartufi e Porcini')">
            <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg> ver
          </button>
        </div>
        <p class="item-desc">mozzarella fiordilatte, cogumelos porcini, queijo asiago e creme de trufa preta</p>
        <div class="item-tags"><span class="tag tag-veg">Vegetariano</span></div>
      </div>
      <div class="item-price">21,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Gamberi</span></div>
        <p class="item-desc">tomate, mozzarella fiordilatte, camarão, tomate cereja marinado e courgette</p>
      </div>
      <div class="item-price">21,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Pugliese</span></div>
        <p class="item-desc">tomate, mozzarella fiordilatte, presunto de Parma 24 meses, ricota, ovo e Parmigiano Reggiano 22 meses</p>
      </div>
      <div class="item-price">22€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Bresaola</span></div>
        <p class="item-desc">tomate, mozzarella fiordilatte, bresaola e Parmigiano Reggiano 22 meses</p>
      </div>
      <div class="item-price">21,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Prosciutto Crudo di Parma e Bufala Campana DOP</span></div>
        <p class="item-desc">tomate, mozzarella di bufala Campana DOP, presunto de Parma 24 meses e rúcula</p>
      </div>
      <div class="item-price">21,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Pancetta e Pecorino</span></div>
        <p class="item-desc">tomate, mozzarella fiordilatte, pancetta e queijo pecorino</p>
      </div>
      <div class="item-price">21,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Fichi e Prosciutto Crudo di Parma</span></div>
        <p class="item-desc">mozzarella fiordilatte, figos e presunto de Parma 24 meses</p>
        <div class="item-tags"><span class="tag tag-veg" style="color:var(--muted)">In stagione</span></div>
      </div>
      <div class="item-price">21€</div>
    </div>
  </section>

  <!-- CALZONI -->
  <section class="section" id="calzoni">
    <div class="section-header">
      <h2 class="section-title">Calzoni</h2>
      <div class="section-line"></div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Classico</span></div>
        <p class="item-desc">tomate, mozzarella fiordilatte, ricota, soprèssa vicentina, fiambre e ovo</p>
      </div>
      <div class="item-price">20,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Bologna</span></div>
        <p class="item-desc">tomate, mozzarella fiordilatte, mortadela e cogumelos</p>
      </div>
      <div class="item-price">19,5€</div>
    </div>

    <div class="item">
      <div class="item-left">
        <div class="item-name-row"><span class="item-name">Franceschini</span></div>
        <p class="item-desc">tomate, mozzarella fiordilatte, ragù, ventricina calabrese picante e azeitonas taggiasche</p>
        <div class="item-tags"><span class="tag tag-hot">Picante</span></div>
      </div>
      <div class="item-price">21,5€</div>
    </div>
  </section>

</main>

<footer>
  <div>
    <span>🌿</span> Vegetariano &nbsp;·&nbsp;
    <span>🌾</span> Sem Glúten disponível &nbsp;·&nbsp;
    <span>🌶</span> Picante
  </div>
  <div style="margin-top:10px">Preços em € · IVA incluído à taxa legal em vigor</div>
  <div style="margin-top:6px;font-size:10px;opacity:.6">Os pratos com vídeo apresentam uma prévia do prato. Carregue em <em>ver</em> para assistir.</div>
</footer>

<!-- VIDEO MODAL -->
<div class="modal" id="modal" onclick="handleClick(event)">
  <div class="modal-box" id="modalBox">
    <div class="modal-header">
      <span class="modal-title" id="modalTitle"></span>
      <button class="modal-close" onclick="closeVideo()" aria-label="Fechar">
        <svg viewBox="0 0 24 24"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
      </button>
    </div>
    <div class="video-wrap">
      <iframe id="videoFrame" allowfullscreen allow="autoplay; encrypted-media"></iframe>
    </div>
  </div>
</div>

<script>
  function openVideo(id, title) {
    const modal = document.getElementById('modal');
    document.getElementById('modalTitle').textContent = title;
    document.getElementById('videoFrame').src = `https://www.youtube.com/embed/${id}?autoplay=1&rel=0`;
    modal.classList.add('active');
    requestAnimationFrame(() => requestAnimationFrame(() => modal.classList.add('visible')));
    document.addEventListener('keydown', onKey);
  }
  function closeVideo() {
    const modal = document.getElementById('modal');
    modal.classList.remove('visible');
    setTimeout(() => { modal.classList.remove('active'); document.getElementById('videoFrame').src = ''; }, 300);
    document.removeEventListener('keydown', onKey);
  }
  function handleClick(e) { if (e.target === document.getElementById('modal')) closeVideo(); }
  function onKey(e) { if (e.key === 'Escape') closeVideo(); }
</script>

</body>
</html>

