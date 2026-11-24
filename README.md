<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Exército Brasileiro de Combate</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Exo+2:wght@500;700;800&family=Roboto:wght@400;500;700&family=Source+Sans+3:wght@600;700&display=swap">
<style>
:root {
  --bg: #050a18;
  --panel-top: #10244f;
  --panel-bottom: #060d20;
  --line: #1b2f5c;
  --fg: #f2f6ff;
  --muted: #8ea3cc;
  --accent: #2bc4f8;
  --accent-ink: #04202e;
  --danger: #ef6a5e;
  --font-display: "Exo 2", "Segoe UI", system-ui, sans-serif;
  --font-body: "Roboto", system-ui, sans-serif;
  --font-label: "Source Sans 3", "Roboto", system-ui, sans-serif;
  color-scheme: dark;
}
html, body { margin: 0; min-height: 100%; }
body {
  background: var(--bg);
  color: var(--fg);
  font-family: var(--font-body);
  font-size: 16px;
  padding-left: max(16px, env(safe-area-inset-left, 0px));
  padding-right: max(16px, env(safe-area-inset-right, 0px));
  overflow-x: hidden;
}
*, *::before, *::after { box-sizing: border-box; }
button { font: inherit; color: inherit; cursor: pointer; }
:focus-visible { outline: 2px solid var(--accent); outline-offset: 3px; }
.gone { display: none !important; }

/* ---------- Entrada ---------- */
.intro {
  position: fixed;
  inset: 0;
  z-index: 10;
  display: grid;
  grid-template-rows: 1fr auto 1fr;
  align-items: center;
  justify-items: center;
  padding-top: env(safe-area-inset-top, 0px);
  padding-bottom: env(safe-area-inset-bottom, 0px);
  padding-left: max(16px, env(safe-area-inset-left, 0px));
  padding-right: max(16px, env(safe-area-inset-right, 0px));
  background: var(--bg);
  overflow: hidden;
}
.intro canvas { position: absolute; inset: 0; width: 100%; height: 100%; z-index: 0; pointer-events: none; }
.intro::after {
  content: "";
  position: absolute;
  inset: 0;
  z-index: 1;
  background: radial-gradient(ellipse at 50% 50%, rgba(5,10,24,.88) 0%, rgba(5,10,24,.55) 45%, rgba(5,10,24,0) 80%);
  pointer-events: none;
}
.intro .word, .intro .enter { position: relative; z-index: 2; }
.word {
  margin: 0;
  font-family: var(--font-display);
  font-weight: 800;
  letter-spacing: .12em;
  text-transform: uppercase;
  text-align: center;
  line-height: 1;
  text-wrap: balance;
  text-shadow: 0 0 24px rgba(43,196,248,.45);
}
.word.top { align-self: end; padding-bottom: 1.2rem; font-size: clamp(1.9rem, 9vw, 5rem); }
.word.bottom { align-self: start; padding-top: 1.2rem; font-size: clamp(1.6rem, 8.5vw, 4.2rem); color: var(--accent); }
.enter {
  display: inline-flex;
  align-items: center;
  gap: .6rem;
  background: var(--accent);
  color: var(--accent-ink);
  border: 0;
  border-radius: 14px;
  padding: 1rem 1.7rem;
  font-family: var(--font-label);
  font-weight: 700;
  font-size: 1rem;
  letter-spacing: .2em;
  text-transform: uppercase;
  box-shadow: 0 0 28px rgba(43,196,248,.45);
  transition: transform .15s ease, box-shadow .15s ease;
}
.enter:hover { transform: translateY(-2px); box-shadow: 0 0 40px rgba(43,196,248,.65); }

/* ---------- Loja ---------- */
.store { max-width: 1100px; margin: 0 auto; padding-block: 1.25rem 4rem; }
.store header {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  gap: .75rem 1.25rem;
  padding-bottom: 1.1rem;
  border-bottom: 1px solid var(--line);
}
.brand {
  background: none;
  border: 0;
  padding: 0;
  text-align: left;
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 1.15rem;
  letter-spacing: .14em;
  text-transform: uppercase;
}
.brand span { color: var(--accent); }
.tabs { display: flex; gap: .5rem; }
.tab {
  background: transparent;
  border: 1px solid var(--line);
  border-radius: 999px;
  padding: .55rem 1.1rem;
  font-family: var(--font-label);
  font-weight: 700;
  letter-spacing: .16em;
  text-transform: uppercase;
  font-size: .82rem;
  color: var(--muted);
}
.tab[aria-selected="true"] { background: var(--accent); border-color: var(--accent); color: var(--accent-ink); }
.notice { margin: 1rem 0 0; color: var(--muted); font-size: .88rem; max-width: 60ch; }
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(min(100%, 300px), 1fr));
  gap: 1rem;
  margin-top: 1.5rem;
  align-items: start;
}
.card {
  min-width: 0;
  border: 1px solid var(--line);
  border-radius: 22px;
  padding: 1.6rem 1.5rem 1.5rem;
  background: linear-gradient(160deg, var(--panel-top) 0%, var(--panel-bottom) 70%);
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.tag {
  font-family: var(--font-label);
  font-weight: 700;
  font-size: .72rem;
  letter-spacing: .3em;
  text-transform: uppercase;
  color: var(--accent);
}
.card h2 {
  margin: 0;
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 1.6rem;
  line-height: 1.15;
  text-wrap: balance;
}
.rows { list-style: none; margin: .25rem 0 0; padding: 0 0 0 1.4rem; }
.rows li {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  gap: 1rem;
  padding: .85rem 0;
  border-bottom: 1px solid var(--line);
  font-weight: 500;
}
.rows li:last-child { border-bottom: 0; }
.rows .n { min-width: 0; }
.price {
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 1.45rem;
  color: var(--accent);
  font-variant-numeric: tabular-nums;
  white-space: nowrap;
}
.rows li.off .n { color: var(--danger); }
.rows li.off .price { color: var(--danger); font-size: 1rem; letter-spacing: .08em; }
.buy {
  align-self: flex-start;
  margin-top: .4rem;
  background: var(--accent);
  color: var(--accent-ink);
  border: 0;
  border-radius: 14px;
  padding: .95rem 1.4rem;
  font-family: var(--font-label);
  font-weight: 700;
  letter-spacing: .2em;
  font-size: .85rem;
  text-transform: uppercase;
  box-shadow: 0 0 22px rgba(43,196,248,.35);
}
.buy:hover { box-shadow: 0 0 32px rgba(43,196,248,.55); }

/* ---------- Janela de compra ---------- */
.overlay {
  position: fixed;
  inset: 0;
  z-index: 20;
  display: grid;
  place-items: center;
  padding: 16px;
  background: rgba(2,5,14,.78);
}
.sheet {
  width: min(100%, 460px);
  max-height: 100%;
  overflow-y: auto;
  border: 1px solid var(--line);
  border-radius: 22px;
  padding: 1.5rem;
  background: linear-gradient(160deg, var(--panel-top) 0%, var(--panel-bottom) 75%);
}
.sheet h3 { margin: .2rem 0 1rem; font-family: var(--font-display); font-size: 1.4rem; line-height: 1.15; }
.choice {
  display: flex;
  align-items: center;
  gap: .8rem;
  padding: .75rem .9rem;
  margin-bottom: .5rem;
  border: 1px solid var(--line);
  border-radius: 12px;
  cursor: pointer;
}
.choice.sel { border-color: var(--accent); background: rgba(43,196,248,.1); }
.choice.off { opacity: .5; cursor: not-allowed; }
.choice input { accent-color: var(--accent); width: 1.1rem; height: 1.1rem; flex: none; }
.choice .n { flex: 1; min-width: 0; }
.choice .price { font-size: 1.15rem; }
.choice.off .price { color: var(--danger); font-size: .8rem; letter-spacing: .08em; }
.total { display: flex; justify-content: space-between; align-items: baseline; margin-top: 1.2rem; color: var(--muted); }
.total strong { font-family: var(--font-display); font-size: 1.6rem; color: var(--fg); }
.actions { display: flex; flex-wrap: wrap; gap: .6rem; margin-top: 1.2rem; }
.ghost { background: transparent; border: 1px solid var(--line); border-radius: 14px; padding: .95rem 1.2rem; font-family: var(--font-label); font-weight: 700; letter-spacing: .16em; font-size: .85rem; text-transform: uppercase; color: var(--muted); }
.steps { margin: 0 0 1.1rem; padding: .9rem 1rem; border: 1px solid var(--accent); border-radius: 12px; background: rgba(43,196,248,.1); line-height: 1.5; }
.steps b { color: var(--accent); }
.pay { margin-top: 1.2rem; }
.pay .lbl { display: block; font-family: var(--font-label); font-weight: 700; font-size: .75rem; letter-spacing: .2em; text-transform: uppercase; color: var(--muted); margin-bottom: .4rem; }
.mail { display: flex; flex-wrap: wrap; align-items: center; gap: .6rem; }
.mail code { flex: 1; min-width: 0; overflow-wrap: anywhere; padding: .8rem .9rem; border: 1px solid var(--line); border-radius: 12px; background: var(--bg); font-size: .95rem; user-select: all; }
.mail .ghost { padding: .8rem 1rem; }

@media (prefers-reduced-motion: reduce) {
  .enter, .enter:hover { transition: none; transform: none; }
}
</style>
</head>
<body>

<section class="intro" id="intro" aria-label="Entrada">
  <canvas id="rain" aria-hidden="true"></canvas>
  <h1 class="word top">Exército Brasileiro</h1>
  <button class="enter" id="enter" type="button">Divisão <span aria-hidden="true">/</span> Patente</button>
  <p class="word bottom">de Combate</p>
</section>

<main class="store gone" id="store">
  <header>
    <button class="brand" id="home" type="button" aria-label="Voltar à entrada">Exército Brasileiro <span>de Combate</span></button>
    <div class="tabs" role="tablist" aria-label="Categoria">
      <button class="tab" role="tab" id="tab-div" aria-selected="true">Divisão</button>
      <button class="tab" role="tab" id="tab-pat" aria-selected="false">Patente</button>
    </div>
  </header>
  <p class="notice">O pagamento é feito fora do site, no e-mail mostrado ao clicar em Comprar. Este é um grupo de jogo, sem ligação com o Exército Brasileiro oficial.</p>
  <div class="grid" id="grid"></div>
</main>

<div class="overlay gone" id="overlay">
  <div class="sheet" role="dialog" aria-modal="true" aria-labelledby="sheet-title" id="sheet"></div>
</div>

<script>
(function () {
  var CUR = "R$";
  var PAY_EMAIL = "pcaldeira1301a@gmail.com";

  /* ===== DIVISÕES: use null no preço para mostrar "NÃO VENDE" ===== */
  var DIVS = [
    { tag: "Divisão à venda · 01", name: "CIE — Centro de Inteligência do Exército", items: [
      ["Comandante", 50], ["Subcomandante", 40], ["Oficiais de Investigação", 25],
      ["Agentes Especializados", 18], ["Agente Formado", 10], ["Agente Praça", 6], ["Agente Estagiário", 3] ] },
    { tag: "Divisão à venda · 02", name: "BAC — Batalhão de Ações de Comando", items: [
      ["Comandante", null], ["Subcomandante", null], ["Oficial de Ação", 35],
      ["Agente de Combate", 25], ["Praça", 10], ["Candidato", 5] ] },
    { tag: "Divisão à venda · 03", name: "FEE — Forças Especiais do Exército", items: [
      ["Candidato", 10.3], ["Praças", 13], ["Graduado Formado", 15], ["Oficiais Especializados", 19],
      ["Subcomandante", 21], ["Comandante", 55] ] },
    { tag: "Divisão à venda · 04", name: "CIGS — Centro de Instrução de Guerra na Selva", items: [
      ["Aluno", null], ["Praças", null], ["Graduado", null], ["Oficiais", null],
      ["Subcomandante", null], ["Comandante", null] ] },
    { tag: "Divisão à venda · 05", name: "PE — Polícia do Exército", items: [
      ["Candidato", null], ["Praça e Graduado", null], ["Oficiais", null],
      ["Subcomandante", null], ["Comandante", null] ] }
  ];

  /* ===== PATENTES ===== */
  var PATS = [
    { name: "Praças Especiais", items: [["Cadete", 20]] },
    { name: "Oficiais Subalternos", items: [["Aspirante a Oficial", 27], ["Segundo-Tenente", 35], ["Primeiro-Tenente", 40]] },
    { name: "Oficiais Intermediários", items: [["Capitão", 47]] },
    { name: "Oficiais Superiores", items: [["Major", 53], ["Tenente-Coronel", 58], ["Coronel", 66]] },
    { name: "Oficiais Generais", items: [["General de Brigada", 78], ["General de Divisão", 89], ["General de Exército", 99]] },
    { name: "Oficiais da Elite", items: [["Elite Militar", 130], ["Elite Secreta", 150], ["Elite Real", 180]] },
    { name: "Vice-Presidente", items: [["Vice-Presidente", 240]] },
    { name: "Alto Comando", items: [["Marechal", 310], ["Sub-Comandante", 360], ["Comandante", 410]] },
    { name: "Presidente", items: [["Presidente", 450]] }
  ];

  function fmt(n) {
    var s = (Math.round(n * 100) / 100).toString().replace(".", ",");
    return s;
  }
  function esc(s) {
    return String(s).replace(/[&<>"]/g, function (c) { return { "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;" }[c]; });
  }
  function $(id) { return document.getElementById(id); }
  function show(el) { el.classList.remove("gone"); }
  function hide(el) { el.classList.add("gone"); }

  var intro = $("intro"), store = $("store"), grid = $("grid");
  var overlay = $("overlay"), sheet = $("sheet");
  var tabs = { div: $("tab-div"), pat: $("tab-pat") };
  var current = "div";
  var rainOn = false;

  /* ---------- Loja ---------- */
  function rowsHtml(items) {
    return items.map(function (it) {
      return it[1] === null
        ? '<li class="off"><span class="n">' + esc(it[0]) + '</span><span class="price">NÃO VENDE</span></li>'
        : '<li><span class="n">' + esc(it[0]) + '</span><span class="price">' + fmt(it[1]) + '</span></li>';
    }).join("");
  }
  function render() {
    var list = current === "div" ? DIVS : PATS;
    grid.innerHTML = list.map(function (g, i) {
      var sells = g.items.some(function (it) { return it[1] !== null; });
      return '<article class="card">' +
        (g.tag ? '<div class="tag">' + esc(g.tag) + '</div>' : '') +
        '<h2>' + esc(g.name) + '</h2>' +
        '<ul class="rows">' + rowsHtml(g.items) + '</ul>' +
        (sells ? '<button class="buy" type="button" data-i="' + i + '">Comprar <span aria-hidden="true">↗</span></button>' : '') +
        '</article>';
    }).join("");
    tabs.div.setAttribute("aria-selected", current === "div" ? "true" : "false");
    tabs.pat.setAttribute("aria-selected", current === "pat" ? "true" : "false");
  }

  /* ---------- Entrar / voltar ---------- */
  function enter() {
    rainOn = false;
    hide(intro);
    show(store);
    render();
    window.scrollTo(0, 0);
  }
  function home() {
    hide(store);
    show(intro);
    startRain();
  }
  $("enter").addEventListener("click", enter);
  $("home").addEventListener("click", home);
  tabs.div.addEventListener("click", function () { current = "div"; render(); });
  tabs.pat.addEventListener("click", function () { current = "pat"; render(); });

  /* ---------- Janela de compra ---------- */
  var opener = null;
  function closeSheet() {
    hide(overlay);
    if (opener) { try { opener.focus(); } catch (e) {} }
  }
  function openBuy(group, btn) {
    opener = btn;
    sheet.innerHTML =
      '<div class="tag">' + esc(group.tag || "Patente") + '</div>' +
      '<h3 id="sheet-title">' + esc(group.name) + '</h3>' +
      '<p class="steps">Quando pagar, vá em <b>compras</b> lá no Exército Brasileiro de Combate e mande o comprovante.</p>' +
      '<form id="order">' +
      group.items.map(function (it, i) {
        var off = it[1] === null;
        return '<label class="choice' + (off ? ' off' : '') + '"><input type="radio" name="item" value="' + i + '"' + (off ? ' disabled' : '') + '>' +
          '<span class="n">' + esc(it[0]) + '</span><span class="price">' + (off ? 'NÃO VENDE' : fmt(it[1])) + '</span></label>';
      }).join("") +
      '<div class="total"><span>Total</span><strong id="total">' + CUR + ' 0</strong></div>' +
      '<div class="pay"><span class="lbl">E-mail para pagamento</span>' +
      '<div class="mail"><code id="mail">' + PAY_EMAIL + '</code><button class="ghost" id="copy" type="button">Copiar</button></div></div>' +
      '<div class="actions"><button class="ghost" id="cancel" type="button">Fechar</button></div>' +
      '</form>';
    show(overlay);
    var form = $("order"), total = $("total"), copyBtn = $("copy");
    form.addEventListener("change", function (e) {
      if (e.target.name === "item") {
        var labels = form.querySelectorAll(".choice");
        for (var i = 0; i < labels.length; i++) labels[i].classList.remove("sel");
        e.target.parentNode.classList.add("sel");
        total.textContent = CUR + " " + fmt(group.items[Number(e.target.value)][1]);
      }
    });
    form.addEventListener("submit", function (e) { e.preventDefault(); });
    $("cancel").addEventListener("click", closeSheet);
    copyBtn.addEventListener("click", function () {
      function selectIt() {
        var r = document.createRange();
        r.selectNodeContents($("mail"));
        var s = window.getSelection();
        s.removeAllRanges();
        s.addRange(r);
        copyBtn.textContent = "Selecionado";
      }
      try {
        navigator.clipboard.writeText(PAY_EMAIL).then(function () { copyBtn.textContent = "Copiado"; }, selectIt);
      } catch (err) { selectIt(); }
    });
  }
  grid.addEventListener("click", function (e) {
    var b = e.target.closest ? e.target.closest(".buy") : null;
    if (!b) return;
    var list = current === "div" ? DIVS : PATS;
    openBuy(list[Number(b.getAttribute("data-i"))], b);
  });
  overlay.addEventListener("click", function (e) { if (e.target === overlay) closeSheet(); });
  document.addEventListener("keydown", function (e) { if (e.key === "Escape" && !overlay.classList.contains("gone")) closeSheet(); });

  /* ---------- Chuva de palavras (se der erro aqui, o botão continua funcionando) ---------- */
  var canvas = $("rain"), ctx = null;
  var WORDS = ["COMANDO", "HONRA", "DIVISÃO", "PATENTE", "DISCIPLINA", "MISSÃO", "COMBATE", "ELITE",
               "CABO", "SOLDADO", "CORONEL", "MAJOR", "CADETE", "GENERAL", "CAPITÃO", "BRIGADA", "TENENTE", "DEVER"];
  var cols = [], W = 0, H = 0, LH = 20, CW = 24, last = 0;

  function pick() { return WORDS[Math.floor(Math.random() * WORDS.length)]; }
  function resize() {
    if (!ctx) return;
    var dpr = Math.min(window.devicePixelRatio || 1, 2);
    W = canvas.clientWidth; H = canvas.clientHeight;
    canvas.width = W * dpr; canvas.height = H * dpr;
    ctx.setTransform(dpr, 0, 0, dpr, 0, 0);
    var n = Math.max(1, Math.floor(W / CW));
    cols = [];
    for (var i = 0; i < n; i++) {
      var w = pick();
      cols.push({ x: (i + .5) * (W / n), word: w, pos: -Math.random() * (H / LH + w.length), speed: 5 + Math.random() * 9 });
    }
    drawFrame(0);
  }
  function drawFrame(dt) {
    ctx.clearRect(0, 0, W, H);
    ctx.font = "700 15px 'Exo 2', monospace";
    ctx.textAlign = "center";
    ctx.textBaseline = "middle";
    var rows = H / LH;
    for (var c = 0; c < cols.length; c++) {
      var col = cols[c], len = col.word.length;
      col.pos += col.speed * dt;
      if (col.pos - len > rows) { col.word = pick(); col.pos = -Math.random() * 10; col.speed = 5 + Math.random() * 9; len = col.word.length; }
      for (var k = 0; k < len; k++) {
        var y = (col.pos - (len - 1 - k)) * LH;
        if (y < -LH || y > H + LH) continue;
        var head = k === len - 1;
        ctx.fillStyle = head ? "rgba(190,240,255,0.95)" : "rgba(43,196,248," + (0.15 + 0.6 * (k / len)).toFixed(2) + ")";
        ctx.fillText(col.word.charAt(k), col.x, y);
      }
    }
  }
  function loop(t) {
    if (!rainOn) return;
    var dt = last ? Math.min((t - last) / 1000, .05) : 0;
    last = t;
    drawFrame(dt);
    requestAnimationFrame(loop);
  }
  function startRain() {
    try {
      if (!ctx) ctx = canvas.getContext("2d");
      last = 0;
      resize();
      var reduce = window.matchMedia && window.matchMedia("(prefers-reduced-motion: reduce)").matches;
      if (!reduce) { rainOn = true; requestAnimationFrame(loop); }
    } catch (err) {}
  }
  window.addEventListener("resize", function () { try { resize(); } catch (e) {} });
  startRain();
})();
</script>
</body>
</html>
