# 少俠・初入江湖（武俠 3D 小遊戲）

用 Three.js 寫的單一 HTML 檔、瀏覽器即可跑的即時動作武俠遊戲。斜俯視、竹林生存戰。

## 怎麼跑起來

不能直接雙擊 `index.html`（用了 ES module 與本機模型載入），要透過小型伺服器：

**方法 A — Python**
```bash
cd wuxia-game
python -m http.server 8000
# 瀏覽器開 http://localhost:8000
```

**方法 B — VS Code（推薦，存檔即自動重整）**
裝 VS Code + Live Server 擴充 → 右鍵 `index.html` → Open with Live Server。

> 需連網（Three.js 由 CDN 載入）。

## 操作
- **W A S D / 方向鍵**：移動
- **滑鼠**：瞄準面向
- **J / 空白鍵 / 滑鼠左鍵**：揮劍（正前方 180° 劍氣）
- **K**：出招（範圍攻擊，耗內力）
- 目標：無限生存，擊敗越多越好，氣血歸零即結束

## 結構
```
wuxia-game/
├── index.html     # 全部遊戲程式（自包含）
├── models/        # 3D 模型 GLB（放進去會自動取代臨時積木角色）
│   └── hero.glb   # 主角（其他：drunkard/thug/thief/boss/elder.glb）
└── README.md
```

## 已完成
即時戰鬥、滑鼠瞄準、180° 劍氣、刀光、命中頓格、走路擺動、出招特效、
怪追擊/血條/傷害飄字、無限生存重生、擊敗計數、戰敗結束。

## 模型生成
角色 GLB 用線上工具（Tripo3D / Meshy 等）以「圖生 3D」產生，下載後改成對應檔名
（hero.glb 等）放進 `models/`，重新整理即自動套用。各角色英文 prompt 見開發紀錄。

## 待辦 / 可擴充
- 換上真模型（目前主角以外仍為臨時積木）
- 難度漸升（擊敗越多怪重生越強）
- 撿道具（包子回血、秘笈學招變強）
- 竹林老者 NPC 對話、多場景

---
給另一台的 Claude Code：直接讀 `index.html` 即可接手，所有邏輯都在那一個檔。
