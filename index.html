<!doctype html>
<html lang="ja">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover" />
  <meta name="theme-color" content="#111827" />
  <title>メモ（フォルダ＋字数）</title>
  <style>
    :root{
      --bg:#0b1020; --panel:#0f172a; --panel2:#111b33;
      --text:#e5e7eb; --muted:#9ca3af; --line:#233056;
      --accent:#60a5fa; --danger:#fb7185;
      --btn:#1f2a4a; --btn2:#223055;
      --shadow: 0 10px 30px rgba(0,0,0,.35);
      --radius: 14px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0; background:linear-gradient(180deg,#050816,#0b1020 40%,#0b1020);
      color:var(--text); font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Noto Sans JP", sans-serif;
      -webkit-tap-highlight-color: transparent;
      touch-action: manipulation;
    }
    button, input, textarea{font:inherit; color:inherit}
    .app{height:100%; display:flex; flex-direction:column}

    /* Top bar */
    .topbar{
      display:flex; align-items:center; gap:10px;
      padding:12px 12px 10px;
      background:rgba(15,23,42,.9);
      border-bottom:1px solid rgba(255,255,255,.06);
      position:sticky; top:0; z-index:10;
      backdrop-filter: blur(10px);
    }
    .crumb{
      flex:1; min-width:0;
      font-weight:700; letter-spacing:.02em;
      white-space:nowrap; overflow:hidden; text-overflow:ellipsis;
    }
    .crumb small{font-weight:600; color:var(--muted)}
    .iconbtn{
      border:1px solid rgba(255,255,255,.08);
      background:linear-gradient(180deg,var(--btn2),var(--btn));
      border-radius:12px;
      padding:10px 12px;
      box-shadow: 0 6px 16px rgba(0,0,0,.25);
      cursor:pointer;
    }
    .iconbtn:active{transform:translateY(1px)}
    .iconbtn.danger{border-color: rgba(251,113,133,.35)}
    .iconbtn.primary{border-color: rgba(96,165,250,.35)}
    .iconbtn[disabled]{opacity:.5; cursor:not-allowed}

    /* List view */
    .view{flex:1; display:none; min-height:0}
    .view.active{display:flex; flex-direction:column}

    .controls{
      padding:12px;
      display:flex; gap:10px; align-items:center; flex-wrap:wrap;
      border-bottom:1px solid rgba(255,255,255,.06);
      background: rgba(15,23,42,.55);
    }
    .field{
      display:flex; gap:8px; align-items:center;
      background: rgba(255,255,255,.04);
      border:1px solid rgba(255,255,255,.07);
      border-radius: 12px;
      padding:10px;
      flex:1;
      min-width: 220px;
    }
    .field input{
      border:0; outline:0; background:transparent; width:100%;
      color:var(--text);
    }
    .hint{color:var(--muted); font-size:12px}

    .grid{
      flex:1; min-height:0; overflow:auto;
      padding:12px;
    }
    .card{
      background: rgba(17,27,51,.72);
      border: 1px solid rgba(255,255,255,.07);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      overflow:hidden;
      margin-bottom: 12px;
    }
    .card h3{
      margin:0; padding:12px 12px 0;
      font-size:14px; color:var(--muted); font-weight:700;
      display:flex; align-items:center; gap:8px;
    }
    .list{padding:10px 10px 12px}
    .row{
      display:flex; align-items:center; gap:10px;
      padding:12px;
      border-radius: 12px;
      border: 1px solid rgba(255,255,255,.06);
      background: rgba(255,255,255,.03);
      cursor:pointer;
      user-select:none;
    }
    .row + .row{margin-top:10px}
    .row:active{transform: translateY(1px)}
    .row .title{
      flex:1; min-width:0;
      font-weight:700;
      white-space:nowrap; overflow:hidden; text-overflow:ellipsis;
    }
    .row .meta{font-size:12px; color:var(--muted); white-space:nowrap}
    .badge{
      font-size:12px; color:#cbd5e1;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(96,165,250,.12);
      padding:4px 8px; border-radius:999px;
    }
    .pillbtn{
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.04);
      border-radius: 999px;
      padding:6px 10px;
      font-size:12px;
      color: #cbd5e1;
      cursor:pointer;
    }
    .pillbtn:active{transform:translateY(1px)}
    .pillbtn.danger{border-color: rgba(251,113,133,.35); color:#fecdd3}
    .empty{
      padding:20px 12px;
      color: var(--muted);
      text-align:center;
    }

    /* Editor view (no overlay-tap bug: display:none when closed) */
    .editor{
      flex:1; min-height:0; display:flex; flex-direction:column;
      padding:12px;
      gap:10px;
    }
    .editorTop{
      display:flex; align-items:center; gap:10px; flex-wrap:wrap;
      background: rgba(255,255,255,.04);
      border:1px solid rgba(255,255,255,.07);
      border-radius: 12px;
      padding:10px;
    }
    .editorTop .name{
      flex:1; min-width:180px;
      border:0; outline:0; background:transparent;
      font-weight:800;
    }
    .counter{
      font-size:12px; color:var(--muted);
      padding:4px 10px; border-radius:999px;
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.03);
      white-space:nowrap;
    }
    textarea{
      flex:1; min-height:0; width:100%;
      resize:none;
      padding:14px 14px;
      border-radius: 14px;
      border:1px solid rgba(255,255,255,.10);
      background: rgba(3,7,18,.55);
      color: var(--text);
      outline:none;
      line-height: 1.6;
      font-size: 15px;
    }
    .footerBtns{
      display:flex; gap:10px; flex-wrap:wrap;
    }
    .toast{
      position: fixed;
      left:50%; bottom:18px; transform: translateX(-50%);
      background: rgba(0,0,0,.75);
      border: 1px solid rgba(255,255,255,.10);
      color: #e5e7eb;
      padding:10px 12px;
      border-radius: 999px;
      font-size: 12px;
      opacity:0; pointer-events:none;
      transition: opacity .15s ease;
      z-index: 9999;
    }
    .toast.show{opacity:1}
  </style>
</head>
<body>
<div class="app">
  <div class="topbar">
    <button class="iconbtn" id="btnUp" title="上へ">⬅︎</button>
    <div class="crumb" id="crumb">ホーム <small id="crumbSmall"></small></div>
    <button class="iconbtn primary" id="btnNewMemo" title="新規メモ">＋メモ</button>
    <button class="iconbtn" id="btnNewFolder" title="新規フォルダ">＋📁</button>
  </div>

  <!-- LIST VIEW -->
  <div class="view active" id="listView">
    <div class="controls">
      <div class="field">
        <span class="hint">検索</span>
        <input id="searchInput" placeholder="タイトル/本文の一部（任意）" />
      </div>
      <button class="pillbtn" id="btnRenameFolder">フォルダ名変更</button>
      <button class="pillbtn danger" id="btnDeleteFolder">フォルダ削除</button>
    </div>

    <div class="grid">
      <div class="card">
        <h3>フォルダ</h3>
        <div class="list" id="folderList"></div>
      </div>

      <div class="card">
        <h3>メモ</h3>
        <div class="list" id="memoList"></div>
      </div>
    </div>
  </div>

  <!-- EDITOR VIEW -->
  <div class="view" id="editorView">
    <div class="editor">
      <div class="editorTop">
        <input class="name" id="memoName" placeholder="メモ名（任意）" />
        <span class="counter" id="charCount">0 文字</span>
        <span class="counter" id="saveState">自動保存</span>
      </div>
      <textarea id="memoBody" placeholder="ここに書く（書式は勝手に変えない）"></textarea>
      <div class="footerBtns">
        <button class="iconbtn" id="btnCloseEditor">一覧へ戻る</button>
        <button class="iconbtn" id="btnDuplicate">複製</button>
        <button class="iconbtn danger" id="btnDeleteMemo">削除</button>
      </div>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<script>
(() => {
  // ====== storage ======
  const STORAGE_KEY = "memo_app_v1_store";

  /** data schema:
   * node: { id, name, folders: [node], memos: [memo] }
   * memo: { id, name, body, createdAt, updatedAt }
   */
  function uid(){
    return Math.random().toString(36).slice(2) + Date.now().toString(36);
  }
  function now(){ return Date.now(); }
  function safeParse(json){
    try{ return JSON.parse(json); }catch(_){ return null; }
  }
  function newNode(name=""){
    return { id: uid(), name, folders: [], memos: [] };
  }
  function newMemo(name=""){
    return { id: uid(), name, body:"", createdAt: now(), updatedAt: now() };
  }

  function loadStore(){
    const raw = localStorage.getItem(STORAGE_KEY);
    const data = raw ? safeParse(raw) : null;
    if (data && data.root) return data;
    // 初期
    const root = newNode("ホーム");
    return { version: 1, root, lastOpen: { pathIds:[root.id], view:"list", memoId:null } };
  }
  function saveStore(){
    try{
      store.lastOpen = { pathIds: path.map(n=>n.id), view: view, memoId: currentMemoId };
      localStorage.setItem(STORAGE_KEY, JSON.stringify(store));
      saveState.textContent = "自動保存";
    }catch(e){
      console.error(e);
      saveState.textContent = "保存失敗";
      toast("保存に失敗（容量/権限）");
    }
  }

  // ====== UI refs ======
  const listView = document.getElementById("listView");
  const editorView = document.getElementById("editorView");
  const crumb = document.getElementById("crumb");
  const crumbSmall = document.getElementById("crumbSmall");

  const btnUp = document.getElementById("btnUp");
  const btnNewMemo = document.getElementById("btnNewMemo");
  const btnNewFolder = document.getElementById("btnNewFolder");
  const btnRenameFolder = document.getElementById("btnRenameFolder");
  const btnDeleteFolder = document.getElementById("btnDeleteFolder");

  const folderList = document.getElementById("folderList");
  const memoList = document.getElementById("memoList");
  const searchInput = document.getElementById("searchInput");

  const memoName = document.getElementById("memoName");
  const memoBody = document.getElementById("memoBody");
  const charCount = document.getElementById("charCount");
  const saveState = document.getElementById("saveState");

  const btnCloseEditor = document.getElementById("btnCloseEditor");
  const btnDuplicate = document.getElementById("btnDuplicate");
  const btnDeleteMemo = document.getElementById("btnDeleteMemo");

  const toastEl = document.getElementById("toast");
  let toastTimer = null;
  function toast(msg){
    toastEl.textContent = msg;
    toastEl.classList.add("show");
    clearTimeout(toastTimer);
    toastTimer = setTimeout(()=>toastEl.classList.remove("show"), 900);
  }

  // ====== state ======
  let store = loadStore();
  const root = store.root;
  let path = [root]; // stack of nodes
  let view = "list"; // "list" | "editor"
  let currentMemoId = null;
  let autosaveTimer = null;

  // ====== helpers ======
  function currentNode(){
    return path[path.length - 1];
  }
  function findNodeById(node, id){
    if (node.id === id) return node;
    for (const f of node.folders){
      const hit = findNodeById(f, id);
      if (hit) return hit;
    }
    return null;
  }
  function findMemoById(node, memoId){
    // search entire tree for memo
    if (!memoId) return null;
    for (const m of node.memos) if (m.id === memoId) return { memo:m, parent:node };
    for (const f of node.folders){
      const hit = findMemoById(f, memoId);
      if (hit) return hit;
    }
    return null;
  }
  function fmtTime(t){
    const d = new Date(t);
    const mm = String(d.getMonth()+1).padStart(2,"0");
    const dd = String(d.getDate()).padStart(2,"0");
    const hh = String(d.getHours()).padStart(2,"0");
    const mi = String(d.getMinutes()).padStart(2,"0");
    return `${mm}/${dd} ${hh}:${mi}`;
  }
  function memoTitle(m){
    const nm = (m.name || "").trim();
    if (nm) return nm;
    const first = (m.body || "").split(/\r?\n/)[0].trim();
    return first ? first.slice(0, 40) : "（無題）";
  }
  function setView(next){
    view = next;
    if (view === "list"){
      listView.classList.add("active");
      editorView.classList.remove("active");
      // editorView is not overlay; safe for tapping
      currentMemoId = null;
      renderList();
    } else {
      listView.classList.remove("active");
      editorView.classList.add("active");
      renderEditor();
    }
    saveStore();
  }

  // ====== rendering ======
  function updateCrumb(){
    const names = path.map((n,i)=> i===0 ? "ホーム" : (n.name || "（無題フォルダ）"));
    crumb.textContent = names.join(" / ");
    crumbSmall.textContent = `（📁${currentNode().folders.length}・📝${currentNode().memos.length}）`;
    btnUp.disabled = (path.length <= 1);
    btnRenameFolder.disabled = (path.length <= 1);
    btnDeleteFolder.disabled = (path.length <= 1);
  }

  function renderList(){
    updateCrumb();
    const q = (searchInput.value || "").trim().toLowerCase();

    // folders
    folderList.innerHTML = "";
    const folders = currentNode().folders.slice().sort((a,b)=> (a.name||"").localeCompare(b.name||"", "ja"));
    if (folders.length === 0){
      folderList.innerHTML = `<div class="empty">フォルダなし</div>`;
    } else {
      for (const f of folders){
        const row = document.createElement("div");
        row.className = "row";
        row.innerHTML = `
          <div class="title">📁 ${escapeHtml(f.name || "（無題フォルダ）")}</div>
          <div class="meta">${f.folders.length} / ${f.memos.length}</div>
        `;
        row.addEventListener("click", () => {
          path.push(f);
          saveStore();
          renderList();
        });
        folderList.appendChild(row);
      }
    }

    // memos
    memoList.innerHTML = "";
    let memos = currentNode().memos.slice().sort((a,b)=> (b.updatedAt||0) - (a.updatedAt||0));
    if (q){
      memos = memos.filter(m => {
        const t = memoTitle(m).toLowerCase();
        const b = (m.body||"").toLowerCase();
        return t.includes(q) || b.includes(q);
      });
    }
    if (memos.length === 0){
      memoList.innerHTML = `<div class="empty">${q ? "検索結果なし" : "メモなし"}</div>`;
    } else {
      for (const m of memos){
        const row = document.createElement("div");
        row.className = "row";
        const title = memoTitle(m);
        const count = (m.body || "").length;
        row.innerHTML = `
          <div class="title">📝 ${escapeHtml(title)}</div>
          <div class="meta">${count}字 · ${fmtTime(m.updatedAt || m.createdAt)}</div>
        `;
        row.addEventListener("click", () => {
          currentMemoId = m.id;
          setView("editor");
        });
        memoList.appendChild(row);
      }
    }
  }

  function renderEditor(){
    updateCrumb();
    const hit = findMemoById(root, currentMemoId);
    if (!hit){
      toast("メモが見つからない");
      setView("list");
      return;
    }
    const m = hit.memo;
    memoName.value = m.name || "";
    memoBody.value = m.body || "";
    updateCounter();
    // focusは邪魔なら外してOK
    memoBody.focus();
  }

  function updateCounter(){
    charCount.textContent = `${memoBody.value.length} 文字`;
  }

  function escapeHtml(s){
    return String(s)
      .replaceAll("&","&amp;")
      .replaceAll("<","&lt;")
      .replaceAll(">","&gt;")
      .replaceAll('"',"&quot;")
      .replaceAll("'","&#039;");
  }

  // ====== actions ======
  function addFolder(){
    const name = prompt("フォルダ名");
    if (name === null) return;
    const nm = name.trim();
    if (!nm){ toast("フォルダ名が空"); return; }
    // 同名は許可（嫌ならここで弾く）
    currentNode().folders.push(newNode(nm));
    saveStore();
    renderList();
    toast("フォルダ追加");
  }

  function renameFolder(){
    if (path.length <= 1) return;
    const cur = currentNode();
    const name = prompt("フォルダ名変更", cur.name || "");
    if (name === null) return;
    cur.name = name.trim();
    saveStore();
    renderList();
    toast("変更した");
  }

  function deleteFolder(){
    if (path.length <= 1) return;
    const cur = currentNode();
    const ok = confirm(`このフォルダを削除？\n「${cur.name || "（無題）"}」\n中身も全部消える`);
    if (!ok) return;
    const parent = path[path.length - 2];
    parent.folders = parent.folders.filter(f => f.id !== cur.id);
    path.pop();
    saveStore();
    renderList();
    toast("削除した");
  }

  function addMemo(){
    const m = newMemo("");
    currentNode().memos.push(m);
    saveStore();
    currentMemoId = m.id;
    setView("editor");
    toast("メモ作成");
  }

  function closeEditor(){
    setView("list");
  }

  function deleteMemo(){
    const hit = findMemoById(root, currentMemoId);
    if (!hit) return;
    const title = memoTitle(hit.memo);
    if (!confirm(`削除する？\n${title}`)) return;
    hit.parent.memos = hit.parent.memos.filter(x => x.id !== hit.memo.id);
    saveStore();
    setView("list");
    toast("削除した");
  }

  function duplicateMemo(){
    const hit = findMemoById(root, currentMemoId);
    if (!hit) return;
    const src = hit.memo;
    const cp = newMemo(src.name ? (src.name + "（複製）") : "");
    cp.body = src.body || "";
    cp.updatedAt = now();
    hit.parent.memos.push(cp);
    saveStore();
    currentMemoId = cp.id;
    renderEditor();
    toast("複製した");
  }

  function scheduleAutosave(){
    clearTimeout(autosaveTimer);
    saveState.textContent = "編集中…";
    autosaveTimer = setTimeout(() => {
      const hit = findMemoById(root, currentMemoId);
      if (!hit) return;
      const m = hit.memo;
      m.name = memoName.value || "";
      m.body = memoBody.value || "";
      m.updatedAt = now();
      saveStore();
      saveState.textContent = "自動保存";
      // list側の順番に効くので更新
    }, 250);
  }

  function goUp(){
    if (path.length <= 1) return;
    path.pop();
    saveStore();
    renderList();
  }

  // ====== events ======
  btnUp.addEventListener("click", goUp);
  btnNewFolder.addEventListener("click", addFolder);
  btnNewMemo.addEventListener("click", addMemo);
  btnRenameFolder.addEventListener("click", renameFolder);
  btnDeleteFolder.addEventListener("click", deleteFolder);

  searchInput.addEventListener("input", renderList);

  btnCloseEditor.addEventListener("click", closeEditor);
  btnDeleteMemo.addEventListener("click", deleteMemo);
  btnDuplicate.addEventListener("click", duplicateMemo);

  memoBody.addEventListener("input", () => {
    updateCounter();
    scheduleAutosave();
  });
  memoName.addEventListener("input", scheduleAutosave);

  // Android back: editor -> list / folder -> up
  window.addEventListener("popstate", (e) => {
    // popstate fires on history navigation; we keep it simple:
    if (view === "editor"){
      // don't lose content; autosave already happens
      setView("list");
      return;
    }
    if (path.length > 1){
      goUp();
      return;
    }
  });

  // ====== boot ======
  // restore last open
  (function boot(){
    try{
      const last = store.lastOpen;
      if (last && Array.isArray(last.pathIds) && last.pathIds.length){
        // rebuild path from ids
        const ids = last.pathIds;
        const rebuilt = [];
        let cur = findNodeById(root, ids[0]);
        if (cur) rebuilt.push(cur);
        for (let i=1;i<ids.length;i++){
          const next = findNodeById(root, ids[i]);
          if (next) rebuilt.push(next);
        }
        if (rebuilt.length) path = rebuilt;
      }
      renderList();
      // start in list always（安定優先）
      setView("list");
      history.replaceState({app:true}, "", location.href);
    }catch(e){
      console.error(e);
      toast("起動時に復旧した（データは残ってる）");
      setView("list");
    }
  })();
})();
</script>
</body>
</html>
