---
name: file-placement-guide
description: 檔案建置管理規範 - 一個蘿蔔一個坑。AI 在產生任何檔案時，自動放到正確位置，不需要事後整理。
triggers:
  - 創建檔案
  - 生成程式
  - 寫文檔
  - 新增
  - generate
  - create
  - scaffold
---

# 檔案建置管理規範（File Placement Guide）

> **核心原則：一個蘿蔔一個坑**
> AI 在創建任何檔案時，必須先確定正確位置，再寫入。

---

## 🎯 創建檔案前必問三個問題

1. **這是什麼類型的檔案？**（程式/文檔/測試/配置/素材）
2. **它屬於哪個階段？**（研究/規劃/開發/測試/文檔）
3. **專案有沒有對應的資料夾？**（有就放進去，沒有就建一個）

---

## 📁 標準專案結構（和心村專用）

```
project/
│
├── 00-research/              # 📚 研究資料
│   ├── _raw/                 # 原始資料
│   ├── references/           # 參考文獻
│   └── *.md                  # 研究筆記
│
├── 01-knowledge/             # 🧠 知識庫
│   ├── database/             # 結構化數據（JSON, CSV）
│   └── wiki/                 # 知識文章
│
├── 02-ideation/              # 💡 構思
│   ├── ideas/                # 想法筆記
│   └── drafts/               # 草稿
│
├── 03-specs/                 # 📋 規格文檔
│   ├── spec.md               # 規格書
│   ├── plan.md               # 計劃書
│   ├── decisions/            # 決策記錄 (ADR)
│   └── meetings/             # 會議記錄
│
├── 04-src/ 或 src/           # 💻 程式碼
│   ├── components/           # 元件
│   ├── hooks/                # Hooks
│   ├── utils/                # 工具函數
│   ├── types/                # 類型定義
│   └── api/                  # API 相關
│
├── 05-tests/ 或 tests/       # 🧪 測試
│   ├── unit/                 # 單元測試
│   ├── integration/          # 整合測試
│   ├── e2e/                  # 端對端測試
│   └── fixtures/             # 測試數據
│
├── docs/                     # 📖 文檔
│   ├── api/                  # API 文檔
│   ├── guides/               # 使用指南
│   ├── architecture/         # 架構文檔
│   └── CHANGELOG.md          # 變更日誌
│
├── scripts/                  # 🔧 腳本
│   ├── build/                # 建構腳本
│   ├── deploy/               # 部署腳本
│   └── utils/                # 工具腳本
│
├── config/                   # ⚙️ 配置
│   └── *.json, *.yaml        # 各種配置檔
│
├── _archive/                 # 📦 歸檔
├── _temp/                    # 🗑️ 暫存
│
├── CLAUDE.md                 # AI 專案記憶
├── PROJECT_MAP.md            # 專案地圖
└── README.md                 # 專案說明
```

---

## 🗂️ 檔案類型對應表

### 程式碼類

| 檔案類型 | 正確位置 | 命名規範 |
|---------|---------|---------|
| React 元件 | `src/components/` | PascalCase.tsx |
| Hooks | `src/hooks/` | useXxx.ts |
| 工具函數 | `src/utils/` | kebab-case.ts |
| 類型定義 | `src/types/` | kebab-case.ts |
| API Route | `src/api/` 或 `api/` | kebab-case.ts |
| 常數定義 | `src/constants/` | UPPER_CASE.ts |
| 樣式 | `src/styles/` | kebab-case.css |

### 文檔類

| 檔案類型 | 正確位置 | 命名規範 |
|---------|---------|---------|
| API 文檔 | `docs/api/` | API_*.md |
| 架構文檔 | `docs/architecture/` | ARCH_*.md |
| 使用指南 | `docs/guides/` | GUIDE_*.md |
| 調查報告 | `docs/research/` 或 `00-research/` | YYYY-MM-DD_*.md |
| 會議記錄 | `03-specs/meetings/` | YYYY-MM-DD_meeting.md |
| 決策記錄 | `03-specs/decisions/` | ADR-NNN_*.md |

### 測試類

| 檔案類型 | 正確位置 | 命名規範 |
|---------|---------|---------|
| 單元測試 | `tests/unit/` 或 同目錄 | *.test.ts |
| 整合測試 | `tests/integration/` | *.integration.test.ts |
| E2E 測試 | `tests/e2e/` | *.e2e.test.ts |
| 測試數據 | `tests/fixtures/` | *.fixture.json |

### 腳本類

| 檔案類型 | 正確位置 | 命名規範 |
|---------|---------|---------|
| 建構腳本 | `scripts/build/` | build_*.sh |
| 部署腳本 | `scripts/deploy/` | deploy_*.sh |
| 工具腳本 | `scripts/utils/` | *.sh 或 *.py |
| 一次性腳本 | `scripts/oneoff/` | YYYY-MM-DD_*.sh |

### 配置類

| 檔案類型 | 正確位置 |
|---------|---------|
| 環境變數 | `.env.example`（根目錄） |
| TypeScript | `tsconfig.json`（根目錄） |
| ESLint | `.eslintrc.js`（根目錄） |
| 其他配置 | `config/` |

---

## 📝 命名規範

### 檔案命名

| 情境 | 格式 | 範例 |
|------|------|------|
| 日期相關 | `YYYY-MM-DD_description` | `2026-01-29_meeting-notes.md` |
| 版本相關 | `name_vN.ext` | `spec_v2.md` |
| 序號相關 | `NNN_name.ext` | `001_init.sql` |
| 一般檔案 | `kebab-case.ext` | `user-profile.tsx` |

### 資料夾命名

- **全小寫**：`components`, `utils`, `hooks`
- **數字前綴**：`00-research`, `01-knowledge`（表示順序）
- **底線前綴**：`_archive`, `_temp`（表示特殊用途）

---

## ⚠️ 禁止事項

1. ❌ **不要把檔案丟在根目錄**（除了配置檔）
2. ❌ **不要創建重複的資料夾**（先檢查有沒有）
3. ❌ **不要用中文命名程式檔**（文檔可以）
4. ❌ **不要把測試和程式碼混在一起**（除非是 co-located）
5. ❌ **不要創建超過 300 行的檔案**（考慮拆分）

---

## ✅ 創建檔案的正確流程

```
1. 確認類型 → 這是什麼檔案？
       ↓
2. 查對應表 → 應該放哪裡？
       ↓
3. 檢查目錄 → 資料夾存在嗎？
       ↓
4. 命名檔案 → 符合規範嗎？
       ↓
5. 寫入檔案 → 完成！
```

---

## 🔄 範例

### 範例 1：創建新的 React 元件

```
Q: 要創建一個 UserProfile 元件
A:
   類型: React 元件
   位置: src/components/
   命名: UserProfile.tsx
   結果: src/components/UserProfile.tsx ✅
```

### 範例 2：創建調查報告

```
Q: 要寫一份 API 調查報告
A:
   類型: 調查報告
   位置: docs/research/ 或 00-research/
   命名: 2026-01-29_api-investigation.md
   結果: docs/research/2026-01-29_api-investigation.md ✅
```

### 範例 3：創建測試檔案

```
Q: 要為 UserProfile 寫測試
A:
   類型: 單元測試
   位置: tests/unit/ 或 src/components/__tests__/
   命名: UserProfile.test.tsx
   結果: tests/unit/UserProfile.test.tsx ✅
```

---

## 🔗 相關 Skills

- **auto-tidy**: 事後整理（如果沒放對）
- **project-index**: 生成專案索引

---

## 💡 給 AI 的提醒

> **每次創建檔案時，先在心裡問：「這個蘿蔔要放哪個坑？」**
>
> 如果不確定，看這份指南的對應表。
> 如果還是不確定，問用戶確認。

---

*這份規範讓 AI 在創建檔案時「一開始就放對位置」，不需要事後大整理。*
