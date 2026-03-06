<!doctype html>
<html lang="ko">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover" />
  <meta name="theme-color" content="#0b1020" />
  <title>포스설치 메뉴얼</title>
  <style>
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:system-ui,-apple-system,Segoe UI,Roboto,"Noto Sans KR",Arial,sans-serif;
      color:#e8ecff;
      background:
        radial-gradient(1200px 800px at 20% -10%, #1a2c6f 0%, transparent 55%),
        radial-gradient(900px 700px at 110% 10%, #1b5b4a 0%, transparent 55%),
        #0b1020;
    }
    a{color:inherit; text-decoration:none}
    .app{display:grid; grid-template-columns:280px 1fr; min-height:100vh;}

    .side{
      position:sticky; top:0; height:100vh;
      padding:18px;
      border-right:1px solid rgba(255,255,255,.10);
      background:linear-gradient(180deg, rgba(255,255,255,.04), transparent 40%);
    }
    .brand{
      display:flex; gap:12px; align-items:center;
      padding:12px;
      border:1px solid rgba(255,255,255,.10);
      border-radius:16px;
      background:rgba(255,255,255,.03);
      box-shadow:0 12px 40px rgba(0,0,0,.35);
    }
    .logo{
      width:42px; height:42px; border-radius:14px;
      background:linear-gradient(135deg, #7aa2ff, #8ef0d0);
      display:grid; place-items:center;
      color:#07101c; font-weight:900;
      flex:0 0 auto;
    }
    .brand h1{margin:0; font-size:15px; line-height:1.2}
    .brand p{margin:2px 0 0; font-size:12px; color:#aab2d5}

    .nav{margin-top:14px; display:flex; flex-direction:column; gap:8px;}
    .nav a{
      padding:10px 12px; border-radius:14px;
      border:1px solid transparent;
      color:#aab2d5;
      display:flex; gap:10px; align-items:center;
    }
    .nav a:hover{background:rgba(255,255,255,.04); color:#e8ecff;}
    .nav a.active{
      background:rgba(122,162,255,.13);
      border-color:rgba(122,162,255,.28);
      color:#e8ecff;
    }
    .chip{
      font-size:11px; padding:2px 8px; border-radius:999px;
      border:1px solid rgba(255,255,255,.10);
      color:#aab2d5;
      margin-left:auto;
      flex:0 0 auto;
      opacity:.75;
    }

    .main{padding:22px; max-width:1200px; width:100%;}
    .topbar{display:flex; gap:12px; align-items:center; flex-wrap:wrap; margin-bottom:14px;}
    .search{
      flex:1; min-width:0;
      display:flex; align-items:center; gap:10px;
      border:1px solid rgba(255,255,255,.10);
      background:rgba(255,255,255,.03);
      border-radius:999px;
      padding:10px 14px;
    }
    .search input{
      border:0; outline:0; width:100%;
      background:transparent; color:#e8ecff;
      font-size:14px;
    }
    .card{
      border:1px solid rgba(255,255,255,.10);
      border-radius:16px;
      background:rgba(255,255,255,.03);
      box-shadow:0 12px 40px rgba(0,0,0,.35);
      padding:16px;
    }
    .headrow{display:flex; align-items:flex-start; justify-content:space-between; gap:12px; margin-bottom:10px;}
    .mini{
      display:inline-flex; align-items:center; justify-content:center;
      padding:10px 12px;
      border-radius:14px;
      border:1px solid rgba(255,255,255,.14);
      background:rgba(255,255,255,.04);
      color:#e8ecff;
      font-size:13px;
      cursor:pointer;
      user-select:none;
      white-space:nowrap;
    }
    .mini:hover{filter:brightness(1.08);}

    .filters{display:flex; gap:8px; flex-wrap:wrap; margin:0;}
    .fchip{
      display:inline-flex; align-items:center;
      font-size:12px;
      padding:7px 10px;
      border-radius:999px;
      border:1px solid rgba(255,255,255,.14);
      background:rgba(0,0,0,.12);
      color:#aab2d5;
      cursor:pointer;
      user-select:none;
      max-width:100%;
      overflow:hidden;
      text-overflow:ellipsis;
      white-space:nowrap;
    }
    .fchip.active{
      color:#e8ecff;
      border-color:rgba(122,162,255,.35);
      background:rgba(122,162,255,.14);
    }

    .list{display:flex; flex-direction:column; gap:10px; margin-top:12px;}
    details{
      border:1px solid rgba(255,255,255,.10);
      border-radius:14px;
      padding:10px 12px;
      background:rgba(0,0,0,.14);
      overflow:hidden;
    }
    details[open]{background:rgba(0,0,0,.18);}
    summary{cursor:pointer; font-weight:900;}
    summary::-webkit-details-marker{display:none}

    .rowhead{display:flex; align-items:center; gap:10px; flex-wrap:wrap;}
    .step{
      font-size:12px; font-weight:900;
      padding:4px 10px; border-radius:999px;
      border:1px solid rgba(122,162,255,.35);
      background:rgba(122,162,255,.14);
      color:#e8ecff;
      flex:0 0 auto;
    }
    .cat{
      font-size:11px;
      padding:3px 8px;
      border-radius:999px;
      border:1px solid rgba(255,255,255,.12);
      background:rgba(0,0,0,.10);
      color:#aab2d5;
      flex:0 0 auto;
      opacity:.9;
    }
    .meta{margin-top:8px; font-size:12px; color:#aab2d5; word-break:break-word;}
    .content{
      margin-top:10px;
      color:#e8ecff;
      font-size:13px;
      line-height:1.65;
      white-space:pre-wrap;
      word-break:break-word;
    }

    .pillchip{display:flex; gap:6px; flex-wrap:wrap; margin-top:8px;}
    .pillchip span{
      font-size:11px; padding:4px 8px; border-radius:999px;
      border:1px solid rgba(255,255,255,.10);
      color:#aab2d5;
      background:rgba(0,0,0,.10);
      max-width:100%;
      overflow:hidden; text-overflow:ellipsis;
    }

    .preview{
      margin-top:8px;
      color:rgba(232,236,255,.88);
      font-size:12.5px;
      line-height:1.45;
      display:-webkit-box;
      -webkit-line-clamp:2;
      -webkit-box-orient:vertical;
      overflow:hidden;
      word-break:break-word;
      white-space:pre-wrap;
    }
    details[open] .preview{display:none;}

    .empty{
      padding:14px;
      border:1px dashed rgba(255,255,255,.18);
      border-radius:14px;
      color:#aab2d5;
      background:rgba(0,0,0,.10);
    }

    .btnline{
      margin-top:10px;
      display:flex;
      gap:8px;
      flex-wrap:wrap;
      align-items:center;
    }
    .linkbtn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:8px;
      padding:9px 12px;
      border-radius:12px;
      border:1px solid rgba(142,240,208,.28);
      background:rgba(142,240,208,.10);
      color:#dffff5;
      font-size:13px;
      cursor:pointer;
      user-select:none;
      white-space:nowrap;
    }
    .linkbtn:hover{filter:brightness(1.08);}
    .linkbtn.disabled{
      opacity:.45;
      border-color:rgba(255,255,255,.18);
      background:rgba(255,255,255,.06);
      color:#aab2d5;
      cursor:default;
      pointer-events:none;
    }
    .copybtn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:8px;
      padding:9px 12px;
      border-radius:12px;
      border:1px solid rgba(122,162,255,.35);
      background:rgba(122,162,255,.12);
      color:#e8ecff;
      font-size:13px;
      cursor:pointer;
      user-select:none;
      white-space:nowrap;
    }
    .copybtn:hover{filter:brightness(1.08);}

    @media (max-width: 900px){
      .app{grid-template-columns:1fr;}
      .side{
        position:sticky; top:0; height:auto; z-index:10;
        border-right:0;
        border-bottom:1px solid rgba(255,255,255,.10);
        padding:12px;
        backdrop-filter:blur(10px);
        background:rgba(11,16,32,.92);
      }
      .nav{flex-direction:row; gap:8px; margin-top:10px;}
      .nav a{flex:1; justify-content:center; padding:10px 10px;}
      .chip{display:none;}
      .main{padding:14px;}
    }
  </style>
</head>
<body>
<div class="app">
  <aside class="side">
    <div class="brand">
      <div class="logo">POS</div>
      <div>
        <h1>포스설치 메뉴얼</h1>
        <p>설치 설정 순서</p>
      </div>
    </div>

    <nav class="nav">
      <a href="#steps" data-tab="steps" class="active">🧩 설치순서 <span class="chip">Guide</span></a>
    </nav>
  </aside>

  <main class="main">
    <div class="topbar">
      <div class="search">
        🔎 <input id="q" placeholder="검색 (단계/구분/제목/내용/태그)" />
      </div>
      <button class="mini" id="btnReload">새로고침</button>
    </div>

    <section class="card" id="tab-steps">
      <div class="headrow">
        <div style="display:flex; flex-direction:column; gap:10px; min-width:0;">
          <h2 style="margin:0">설치 설정 순서</h2>
          <div class="filters" id="catFilters"></div>
        </div>
        <div class="meta" id="stat"></div>
      </div>
      <div class="list" id="stepsList"></div>
    </section>
  </main>
</div>

<script>
/** ✅ 시트 정보 */
const SHEET_ID = "1p9DzZ7_GR9m5wwQCIRdQIHitPhUCfh3iVLjFF-RfrWE";
const GID = "1399061484";

/** helpers */
const $  = (q)=>document.querySelector(q);
const $$ = (q)=>Array.from(document.querySelectorAll(q));

let itemsCached = [];
let catFilter = "all";

/** 숨김 디버그 상태(화면에 표시 안 함) */
let __debug = {
  tried: [],
  ok: false,
  error: "",
  gvizUrl: "",
  csvUrl: "",
  rows: 0,
  updatedAt: ""
};

function escapeHtml(str){
  return String(str ?? "")
    .replaceAll("&","&amp;").replaceAll("<","&lt;").replaceAll(">","&gt;")
    .replaceAll('"',"&quot;").replaceAll("'","&#039;");
}
function isLikelyUrl(s){
  const t = String(s||"").trim();
  if(!t) return false;
  if(/^https?:\/\//i.test(t)) return true;
  if(t.includes("docs.google.com") || t.includes("drive.google.com")) return true;
  return false;
}
function normUrl(s){
  const t = String(s||"").trim();
  if(!t) return "";
  if(/^https?:\/\//i.test(t)) return t;
  return "https://" + t;
}
function toNumberish(s){
  const t = String(s||"").trim();
  if(!t) return NaN;
  const n = parseFloat(t.replace(/[^\d.]/g,""));
  return Number.isFinite(n) ? n : NaN;
}
function normalizeHeader(s){
  return String(s||"").trim().toLowerCase().replace(/\s+/g,"");
}

/** route (단일 탭) */
function setTabUI(){
  $$(".nav a").forEach(a=>a.classList.toggle("active", true));
  $("#tab-steps").style.display  = "block";
}
window.addEventListener("hashchange", ()=> setTabUI());

/** 1) gviz(JSONP) */
function loadByGviz(tq){
  return new Promise((resolve, reject) => {
    const cbName = "__gviz_cb_" + Math.random().toString(36).slice(2) + Date.now();
    const query = encodeURIComponent(tq || "select A,B,C,D,E,F limit 3000");
    const tqx = encodeURIComponent(`out:json;responseHandler:${cbName}`);
    const url = `https://docs.google.com/spreadsheets/d/${SHEET_ID}/gviz/tq?gid=${encodeURIComponent(GID)}&tq=${query}&tqx=${tqx}&_=${Date.now()}`;
    __debug.gvizUrl = url;

    const script = document.createElement("script");
    const timer = setTimeout(() => { cleanup(); reject(new Error("GVIZ timeout")); }, 12000);

    function cleanup(){
      clearTimeout(timer);
      try{ delete window[cbName]; }catch(e){}
      if(script.parentNode) script.parentNode.removeChild(script);
    }

    window[cbName] = (resp) => {
      try{
        cleanup();
        if(!resp || resp.status !== "ok"){
          throw new Error(resp?.errors?.[0]?.message || "GVIZ load failed");
        }
        const rows = (resp.table.rows||[]).map(r => (r.c||[]).map(cell => {
          if(!cell) return "";
          const f = (cell.f != null) ? String(cell.f).trim() : "";
          const v = (cell.v != null) ? String(cell.v).trim() : "";
          return f || v;
        }));
        resolve(rows);
      }catch(e){ reject(e); }
    };

    script.src = url;
    script.async = true;
    script.onerror = () => { cleanup(); reject(new Error("GVIZ network")); };
    document.head.appendChild(script);
  });
}

/** 2) Publish CSV fallback */
function buildCsvUrl(){
  return `https://docs.google.com/spreadsheets/d/${encodeURIComponent(SHEET_ID)}/pub?gid=${encodeURIComponent(GID)}&single=true&output=csv`;
}
function parseCSV(text){
  const rows = [];
  let row = [];
  let cur = "";
  let inQuotes = false;

  for(let i=0;i<text.length;i++){
    const ch = text[i];
    const next = text[i+1];

    if(inQuotes){
      if(ch === '"' && next === '"'){ cur += '"'; i++; continue; }
      if(ch === '"'){ inQuotes = false; continue; }
      cur += ch; continue;
    }else{
      if(ch === '"'){ inQuotes = true; continue; }
      if(ch === ','){ row.push(cur); cur=""; continue; }
      if(ch === '\n'){
        row.push(cur); cur="";
        rows.push(row.map(x=>String(x).replace(/\r/g,"")));
        row=[]; continue;
      }
      cur += ch;
    }
  }
  row.push(cur);
  rows.push(row.map(x=>String(x).replace(/\r/g,"")));
  return rows.filter(r => r.some(c => String(c).trim()!==""));
}
async function loadByCsv(){
  const url = buildCsvUrl();
  __debug.csvUrl = url;
  const res = await fetch(url, { cache: "no-store" });
  const text = await res.text();

  if(!res.ok) throw new Error(`CSV HTTP ${res.status}`);
  if(/<html/i.test(text) && /google/i.test(text)) {
    throw new Error("CSV 응답이 아닌 페이지(권한/게시 설정 확인 필요)");
  }
  return parseCSV(text);
}

/** rows -> items (A~F, 헤더 자동 인식) */
function buildColMap(headerRow){
  const cols = (headerRow||[]).map(normalizeHeader);
  const pick = (...keys)=>{
    for(const k of keys){
      const idx = cols.findIndex(x => x===normalizeHeader(k));
      if(idx>=0) return idx;
    }
    return -1;
  };
  return {
    stepIdx:  pick("단계","step","순서","no","번호"),
    catIdx:   pick("구분","분류","카테고리","category","type"),
    titleIdx: pick("제목","title","항목","작업"),
    bodyIdx:  pick("내용","설명","detail","desc","방법"),
    linkIdx:  pick("링크","url","자료","첨부","참고"),
    tagIdx:   pick("태그","tags","키워드")
  };
}
function rowsToItems(rows){
  const clean = (rows||[]).filter(r => (r||[]).some(x => String(x).trim() !== ""));
  if(!clean.length) return [];

  const first = clean[0].map(String);
  const firstNorm = first.map(normalizeHeader).join("|");
  const looksHeader =
    firstNorm.includes("단계") || firstNorm.includes("제목") || firstNorm.includes("내용") || firstNorm.includes("링크") ||
    firstNorm.includes("분류") || firstNorm.includes("구분");

  let dataRows = clean;
  let map = null;

  if(looksHeader){
    map = buildColMap(clean[0]);
    dataRows = clean.slice(1);
  }

  const idxOr = (idx, fb)=> (idx!=null && idx>=0 ? idx : fb);

  const stepI  = idxOr(map?.stepIdx,  0);
  const catI   = idxOr(map?.catIdx,   1);
  const titleI = idxOr(map?.titleIdx, 2);
  const bodyI  = idxOr(map?.bodyIdx,  3);
  const linkI  = idxOr(map?.linkIdx,  4);
  const tagI   = idxOr(map?.tagIdx,   5);

  const items = dataRows.map((r, i)=>({
    rowNo: i+2,
    step:  String(r[stepI]||"").trim(),
    cat:   String(r[catI]||"").trim(),
    title: String(r[titleI]||"").trim(),
    body:  String(r[bodyI]||"").trim(),
    link:  String(r[linkI]||"").trim(),
    tags:  String(r[tagI]||"").trim(),
  })).filter(x => x.step || x.cat || x.title || x.body || x.link || x.tags);

  items.sort((a,b)=>{
    const an = toNumberish(a.step);
    const bn = toNumberish(b.step);
    const aOK = Number.isFinite(an);
    const bOK = Number.isFinite(bn);
    if(aOK && bOK) return an - bn;
    if(aOK && !bOK) return -1;
    if(!aOK && bOK) return 1;
    return String(a.step).localeCompare(String(b.step));
  });

  return items;
}

/** render */
function uniqCats(items){
  const set = new Set();
  items.forEach(x=>{
    const c = (x.cat||"").trim();
    if(c) set.add(c);
  });
  return Array.from(set);
}
function renderFilters(items){
  const wrap = $("#catFilters");
  const cats = uniqCats(items);

  wrap.innerHTML = "";
  const all = document.createElement("div");
  all.className = "fchip" + (catFilter==="all" ? " active" : "");
  all.dataset.f = "all";
  all.textContent = "전체";
  wrap.appendChild(all);

  cats.forEach(c=>{
    const el = document.createElement("div");
    el.className = "fchip" + (catFilter===c ? " active" : "");
    el.dataset.f = c;
    el.textContent = c;
    wrap.appendChild(el);
  });
}
function matchesQuery(x, q){
  if(!q) return true;
  const blob = `${x.step} ${x.cat} ${x.title} ${x.body} ${x.tags} ${x.link}`.toLowerCase();
  return blob.includes(q);
}
function renderSteps(items){
  const list = $("#stepsList");
  const q = ($("#q").value||"").trim().toLowerCase();

  const filtered = items.filter(x=>{
    if(catFilter!=="all" && String(x.cat||"").trim() !== catFilter) return false;
    return matchesQuery(x, q);
  });

  $("#stat").textContent = `표시: ${filtered.length} / 전체: ${items.length}`;

  list.innerHTML = "";
  if(!filtered.length){
    list.innerHTML = `<div class="empty">표시할 항목이 없습니다.</div>`;
    return;
  }

  filtered.forEach((x, idx)=>{
    const d = document.createElement("details");

    const tagArr = (x.tags||"").split(",").map(t=>t.trim()).filter(Boolean);
    const tagsHtml = tagArr.length
      ? `<div class="pillchip">${tagArr.map(t=>`<span>#${escapeHtml(t)}</span>`).join("")}</div>`
      : "";

    const title = x.title || (x.body ? x.body.split("\n")[0].slice(0,40) : `설치 항목 ${idx+1}`);
    const preview = (x.body||"").trim();

    const hasLink = isLikelyUrl(x.link);
    const url = hasLink ? normUrl(x.link) : "";

    d.innerHTML = `
      <summary>
        <div class="rowhead">
          <span class="step">${escapeHtml(x.step || (idx+1))}</span>
          ${x.cat ? `<span class="cat">${escapeHtml(x.cat)}</span>` : ``}
          <span>${escapeHtml(title)}</span>
        </div>
        ${preview ? `<div class="preview">${escapeHtml(preview)}</div>` : ``}
      </summary>

      ${tagsHtml}
      ${x.body ? `<div class="content">${escapeHtml(x.body)}</div>` : ``}

      <div class="btnline">
        <a class="linkbtn ${hasLink ? "" : "disabled"}" href="${hasLink ? escapeHtml(url) : "#"}" target="_blank" rel="noopener">
          📎 자료 링크
        </a>

        <button class="copybtn" data-copy="${escapeHtml([`[${x.step}] ${x.cat} - ${title}`, x.body, url].filter(Boolean).join("\n"))}">
          📋 내용 복사
        </button>

        ${hasLink ? `<span class="meta" style="margin:0;">${escapeHtml(url)}</span>` : ``}
      </div>
    `;

    list.appendChild(d);
  });
}

/** load (GVIZ → CSV fallback) */
async function reload(){
  __debug = { tried: [], ok:false, error:"", gvizUrl:"", csvUrl:"", rows:0, updatedAt:"" };

  $("#stat").textContent = "불러오는 중…";
  $("#stepsList").innerHTML = `<div class="empty">불러오는 중…</div>`;

  try{
    __debug.tried.push("GVIZ");
    const rows = await loadByGviz("select A,B,C,D,E,F limit 3000");
    itemsCached = rowsToItems(rows);
    __debug.ok = true;
  }catch(e1){
    __debug.error = e1?.message ? String(e1.message) : String(e1);
    try{
      __debug.tried.push("CSV");
      const csvRows = await loadByCsv();
      itemsCached = rowsToItems(csvRows);
      __debug.ok = true;
      __debug.error = "";
    }catch(e2){
      __debug.ok = false;
      __debug.error = (e2?.message ? String(e2.message) : String(e2));
      itemsCached = [];
    }
  }

  __debug.rows = itemsCached.length;
  __debug.updatedAt = new Date().toLocaleString();

  renderFilters(itemsCached);
  renderSteps(itemsCached);
}

/** events */
$("#btnReload").addEventListener("click", reload);
$("#q").addEventListener("input", ()=> renderSteps(itemsCached));
$("#catFilters").addEventListener("click", (ev)=>{
  const btn = ev.target.closest(".fchip");
  if(!btn) return;
  catFilter = btn.dataset.f || "all";
  $$("#catFilters .fchip").forEach(x=>x.classList.toggle("active", x.dataset.f === catFilter));
  renderSteps(itemsCached);
});
document.addEventListener("click", async (ev)=>{
  const btn = ev.target.closest(".copybtn");
  if(!btn) return;
  const text = btn.dataset.copy || "";
  try{
    await navigator.clipboard.writeText(text);
    btn.textContent = "✅ 복사됨";
    setTimeout(()=> btn.textContent = "📋 내용 복사", 900);
  }catch(e){
    const ta = document.createElement("textarea");
    ta.value = text;
    document.body.appendChild(ta);
    ta.select();
    try{ document.execCommand("copy"); }catch(_){}
    document.body.removeChild(ta);
    btn.textContent = "✅ 복사됨";
    setTimeout(()=> btn.textContent = "📋 내용 복사", 900);
  }
});

/** 숨김 디버그: Ctrl + Shift + D */
document.addEventListener("keydown", (e)=>{
  if(e.ctrlKey && e.shiftKey && (e.key==="D" || e.key==="d")){
    console.log("[POS MANUAL DEBUG]", __debug);
    alert("디버그 로그를 콘솔(F12)에서 확인하세요.");
  }
});

/** init */
setTabUI();
reload();
</script>
</body>
</html>
