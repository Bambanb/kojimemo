<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>極秘レシピ</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Noto Sans JP", sans-serif;
            background: #f2f4f8;
            color: #333;
        }

        .app-container {
            max-width: 1080px;
            margin: 16px auto;
            padding: 8px;
        }

        .app-card {
            background: #fff;
            border-radius: 16px;
            box-shadow: 0 4px 14px rgba(0,0,0,0.06);
            overflow: hidden;
        }

        .app-header {
            background: #2f80ed;
            color: #fff;
            padding: 12px 16px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .app-header-title {
            font-size: 18px;
            font-weight: 600;
        }

        .app-body {
            display: flex;
            min-height: calc(100vh - 120px);
        }

        @media (max-width: 800px) {
            .app-body {
                flex-direction: column;
            }
        }

        .sidebar {
            width: 260px;
            border-right: 1px solid #eef1f6;
            padding: 12px;
            background: #f8fafc;
        }

        @media (max-width: 800px) {
            .sidebar {
                width: 100%;
                border-right: none;
                border-bottom: 1px solid #eef1f6;
            }
        }

        .sidebar-title {
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .folder-list {
            margin-bottom: 16px;
        }

        .folder-item {
            padding: 8px 10px;
            border-radius: 8px;
            background: #ffffff;
            border: 1px solid #e1e6ef;
            margin-bottom: 6px;
            font-size: 13px;
            cursor: pointer;
        }

        .folder-item.active {
            background: #e3f1ff;
            border-color: #2f80ed;
            font-weight: 600;
        }

        .folder-input {
            width: 100%;
            padding: 8px 10px;
            margin-bottom: 6px;
            font-size: 13px;
            border-radius: 8px;
            border: 1px solid #d0d7e2;
        }

        .primary-btn {
            width: 100%;
            padding: 8px 10px;
            border-radius: 8px;
            border: none;
            background: #2f80ed;
            color: #fff;
            font-size: 13px;
            font-weight: 600;
        }

        .editor {
            flex: 1;
            padding: 12px;
            display: flex;
            flex-direction: column;
            min-width: 0;
        }

        .editor-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 8px;
            margin-bottom: 8px;
        }

        .editor-header h2 {
            font-size: 15px;
            font-weight: 600;
        }

        .editor-header-right {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .char-count {
            font-size: 12px;
            color: #666;
        }

        .fullscreen-toggle {
            font-size: 11px;
            padding: 4px 8px;
            border-radius: 6px;
            border: 1px solid #d0d7e2;
            background: #fff;
        }

        .editor-main {
            display: flex;
            flex: 1;
            min-height: 0;
            gap: 12px;
        }

        @media (max-width: 800px) {
            .editor-main {
                flex-direction: column;
            }
        }
        .editor-pane {
            flex: 1;
            display: flex;
            flex-direction: column;
            min-width: 0;
        }

        .memo-title {
            width: 100%;
            padding: 8px 10px;
            margin-bottom: 6px;
            font-size: 14px;
            border-radius: 8px;
            border: 1px solid #d0d7e2;
        }

        .memo-text {
            flex: 1;
            padding: 10px;
            font-size: 14px;
            border-radius: 8px;
            border: 1px solid #d0d7e2;
            resize: none;
            line-height: 1.6;
            min-height: 200px;
        }

        .editor-actions {
            margin-top: 8px;
            display: flex;
            gap: 8px;
        }

        .secondary-btn {
            flex: 1;
            padding: 8px 10px;
            border-radius: 8px;
            border: 1px solid #d0d7e2;
            background: #fff;
            font-size: 13px;
        }

        .primary-small-btn {
            flex: 1;
            padding: 8px 10px;
            border-radius: 8px;
            border: none;
            background: #2f80ed;
            color: #fff;
            font-size: 13px;
        }

        .memo-list-pane {
            width: 220px;
            border-left: 1px solid #eef1f6;
            padding-left: 10px;
        }

        @media (max-width: 800px) {
            .memo-list-pane {
                width: 100%;
                border-left: none;
                border-top: 1px solid #eef1f6;
                padding-left: 0;
                padding-top: 10px;
            }
        }

        .memo-list-title {
            font-size: 13px;
            font-weight: 600;
            margin-bottom: 4px;
        }

        .memo-list {
            margin-top: 4px;
            max-height: 260px;
            overflow-y: auto;
        }

        .memo-list-item {
            padding: 6px 8px;
            border-radius: 6px;
            border: 1px solid #e1e6ef;
            margin-bottom: 4px;
            font-size: 12px;
            background: #fff;
        }

        .memo-list-item-title {
            font-weight: 600;
            margin-bottom: 2px;
        }

        .memo-list-item-meta {
            font-size: 11px;
            color: #777;
            display: flex;
            justify-content: space-between;
        }

        .memo-list-item-actions {
            margin-top: 4px;
            display: flex;
            gap: 4px;
        }

        .list-btn {
            flex: 1;
            padding: 3px 4px;
            font-size: 11px;
            border-radius: 4px;
            border: 1px solid #d0d7e2;
            background: #fff;
        }

        body.editor-fullscreen {
            overflow: hidden;
        }

        .editor.fullscreen {
            position: fixed;
            inset: 0;
            max-width: 100%;
            margin: 0;
            border-radius: 0;
            box-shadow: none;
            z-index: 999;
            background: #ffffff;
            display: flex;
            flex-direction: column;
        }

        .editor.fullscreen .editor-main {
            flex: 1;
            min-height: 0;
        }

        .editor.fullscreen .memo-text {
            min-height: 0;
        }
    </style>
</head>
<body>
<div class="app-container">
    <div class="app-card">
        <div class="app-header">
            <span>📝</span>
            <span class="app-header-title">極秘レシピ</span>
        </div>
        <div class="app-body">
            <div class="sidebar">
                <div class="sidebar-title">🔪 厨房</div>
                <div id="folderList" class="folder-list"></div>
                <input id="newFolderName" class="folder-input" placeholder="新しい料理">
                <button class="primary-btn" onclick="addFolder()">料理を追加</button>
            </div>

            <div class="editor" id="editorArea">
                <div class="editor-header">
                    <h2 id="currentFolderName">料理を選べ</h2>
                    <div class="editor-header-right">
                        <div class="char-count">文字数: <span id="charCount">0</span></div>
                        <button class="fullscreen-toggle" onclick="toggleFullscreen()">✂ 掻っ捌く</button>
                    </div>
                </div>
                <div class="editor-main">
                    <div class="editor-pane">
                        <input id="memoTitle" class="memo-title" placeholder="料理名">
                        <textarea id="memoText" class="memo-text" placeholder="覚悟しやがれ……"></textarea>
                        <div class="editor-actions">
                            <button class="secondary-btn" onclick="clearMemo()">解体</button>
                            <button class="primary-small-btn" onclick="saveMemo()">冷蔵</button>
                        </div>
                    </div>

                    <div class="memo-list-pane">
                        <div class="memo-list-title">在庫一覧</div>
                        <div id="memoList" class="memo-list"></div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

<script>
    const STORAGE_KEY = "kojimemo_data_v1";

    let appData = {
        folders: {},
        currentFolder: null
    };

    function loadFromStorage() {
        try {
            const saved = localStorage.getItem(STORAGE_KEY);
            if (saved) {
                appData = JSON.parse(saved);
            } else {
                appData.folders = {
                    "魚": [],
                    "肉A": [],
                    "肉B": []
                };
                appData.currentFolder = "レシピ";
            }
        } catch (e) {
            console.error("load error", e);
        }
    }

    function saveToStorage() {
        try {
            localStorage.setItem(STORAGE_KEY, JSON.stringify(appData));
        } catch (e) {
            console.error("save error", e);
        }
    }

    function renderFolders() {
        const folderList = document.getElementById("folderList");
        folderList.innerHTML = "";

        Object.keys(appData.folders).forEach(folderName => {
            const div = document.createElement("div");
            div.className = "folder-item" + (folderName === appData.currentFolder ? " active" : "");
            div.textContent = folderName;
            div.onclick = () => selectFolder(folderName);
            folderList.appendChild(div);
        });

        if (!appData.currentFolder || !appData.folders[appData.currentFolder]) {
            const first = Object.keys(appData.folders)[0];
            appData.currentFolder = first || null;
        }

        const currentNameEl = document.getElementById("currentFolderName");
        currentNameEl.textContent = appData.currentFolder
            ? `📁 ${appData.currentFolder}`
            : "料理を選べ";

        renderMemoList();
    }

    function selectFolder(folderName) {
        appData.currentFolder = folderName;
        saveToStorage();
        renderFolders();
        clearMemo();
    }

    function addFolder() {
        const input = document.getElementById("newFolderName");
        const name = input.value.trim();
        if (!name) return;
        if (appData.folders[name]) {
            alert("メニューがダブった");
            return;
        }
        appData.folders[name] = [];
        appData.currentFolder = name;
        input.value = "";
        saveToStorage();
        renderFolders();
        clearMemo();
    }
    function renderMemoList() {
        const memoList = document.getElementById("memoList");
        memoList.innerHTML = "";

        if (!appData.currentFolder) return;

        const memos = appData.folders[appData.currentFolder];

        if (!memos || memos.length === 0) {
            memoList.innerHTML = `<div style="font-size:12px; color:#888;">何もねえ</div>`;
            return;
        }

        memos.forEach((memo, index) => {
            const item = document.createElement("div");
            item.className = "memo-list-item";

            const title = document.createElement("div");
            title.className = "memo-list-item-title";
            title.textContent = memo.title || "(無題)";

            const meta = document.createElement("div");
            meta.className = "memo-list-item-meta";
            meta.innerHTML = `
                <span>${memo.length} 文字</span>
                <span>${new Date(memo.time).toLocaleString()}</span>
            `;

            const actions = document.createElement("div");
            actions.className = "memo-list-item-actions";

            const openBtn = document.createElement("button");
            openBtn.className = "list-btn";
            openBtn.textContent = "調理";
            openBtn.onclick = () => loadMemo(index);

            const delBtn = document.createElement("button");
            delBtn.className = "list-btn";
            delBtn.textContent = "解体";
            delBtn.onclick = () => deleteMemo(index);

            actions.appendChild(openBtn);
            actions.appendChild(delBtn);

            item.appendChild(title);
            item.appendChild(meta);
            item.appendChild(actions);

            memoList.appendChild(item);
        });
    }

    function saveMemo() {
        if (!appData.currentFolder) {
            alert("料理を選べ");
            return;
        }

        const title = document.getElementById("memoTitle").value.trim();
        const content = document.getElementById("memoText").value;
        const length = content.length;

        const memo = {
            title: title,
            content: content,
            length: length,
            time: Date.now()
        };

        appData.folders[appData.currentFolder].push(memo);

        saveToStorage();
        renderMemoList();
        clearMemo();
    }

    function loadMemo(index) {
        const memo = appData.folders[appData.currentFolder][index];
        document.getElementById("memoTitle").value = memo.title;
        document.getElementById("memoText").value = memo.content;
        updateCount();
    }

    function deleteMemo(index) {
        if (!confirm("解体されてえんだな？")) return;
        appData.folders[appData.currentFolder].splice(index, 1);
        saveToStorage();
        renderMemoList();
        clearMemo();
    }
    function clearMemo() {
        document.getElementById("memoTitle").value = "";
        document.getElementById("memoText").value = "";
        updateCount();
    }

    function updateCount() {
        const text = document.getElementById("memoText").value;
        document.getElementById("charCount").textContent = text.length;
    }

    document.getElementById("memoText").addEventListener("input", updateCount);

    function toggleFullscreen() {
        const editor = document.getElementById("editorArea");
        const btn = document.querySelector(".fullscreen-toggle");

        if (!editor) return;

        if (editor.classList.contains("fullscreen")) {
            editor.classList.remove("fullscreen");
            document.body.classList.remove("editor-fullscreen");
            btn.textContent = "⬜ 解剖";
        } else {
            editor.classList.add("fullscreen");
            document.body.classList.add("editor-fullscreen");
            btn.textContent = "❌ 失せろ";
        }
    }

    loadFromStorage();
    renderFolders();
    updateCount();
</script>

</body>
</html>
