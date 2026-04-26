---
name: ignition-jython-script
description: "This skill should be used when the user asks to write Ignition Jython scripts, create functions for tag operations, database queries, or Perspective integrations, mentions generating Ignition automation code, or needs code that follows Ignition 8.1 conventions (Jython 2.7 + try/except + logger + scope, no f-strings, complete API namespaces). Use this skill for: writing tag read/write functions, database Named Query scripts, Message Handlers, Gateway-level automation, Perspective bindings, or any script that must comply with team standards. Do NOT trigger when the user is asking about Ignition configuration, UI design without scripting, or questions about official Ignition documentation alone."
---

# Ignition 8.1 Jython 腳本產生器

撰寫符合規範的 Ignition SCADA Jython 腳本。此 Skill 遵循 Ignition 8.1 團隊標準，確保一致的程式碼風格、安全的異常處理，與最佳效能實踐。

## 核心規範

遵循 Ignition 8.1 標準化規範。詳細規則參考 [技術規範](./references/copilot-instructions-ignition-jython.md)。

### 基本要求
- **語言版本**：Jython 2.7 （Python 2.7 相容）
- **執行環境**：Ignition SCADA 8.1
- **架構優先**：Perspective > Vision

### 禁止項目
- ❌ f-string 格式化（使用 `"{}".format()` 或字串連接）
- ❌ 直接呼叫 `system.tag.read()`（改用 `readBlocking()` 或 `readAsync()`）
- ❌ UI 層直接拼 SQL（使用 Named Query 代替）
- ❌ 未捕捉的異常（必須使用 try/except）

### 必須使用的模式
```python
def ReadTag(tagPath):
    logger = system.util.getLogger("Tag")
    try:
        return system.tag.readBlocking([tagPath])[0].value
    except Exception as e:
        logger.error(str(e))
        return None
```

## 常見情境與範例

### 情境 1：讀取 Tag 值
**輸入**：「建立函式讀取 'Enterprise/Plant1/Area1/Line1/Equipment1/Temperature' 這個 Tag」  
**輸出**：
```python
def read_temperature():
    logger = system.util.getLogger("Temperature")
    try:
        result = system.tag.readBlocking(["Enterprise/Plant1/Area1/Line1/Equipment1/Temperature"])
        return result[0].value if result[0].quality.isGood() else None
    except Exception as e:
        logger.error("Failed to read temperature: " + str(e))
        return None
```

### 情境 2：寫入 Tag 值
**輸入**：「寫入生產線速度設定值（SpeedSetpoint），確保寫入成功」  
**輸出**：
```python
def write_speed_setpoint(lineId, speed_value):
    logger = system.util.getLogger("Speed")
    try:
        tag_path = "Enterprise/Plant1/Area1/Line{}/Equipment1/SpeedSetpoint".format(lineId)
        result = system.tag.writeBlocking([tag_path], [speed_value])
        if not result[0]:
            logger.warn("Failed to write speed setpoint")
        return result[0]
    except Exception as e:
        logger.error("Write error: " + str(e))
        return False
```

### 情境 3：Database 查詢
**輸入**：「使用 Named Query 'GetProductionStats' 查詢生產統計，參數是 lineId」  
**輸出**：
```python
def query_production_stats(line_id):
    logger = system.util.getLogger("Database")
    try:
        dataset = system.db.runNamedQuery("GetProductionStats", {"lineId": line_id})
        return dataset
    except Exception as e:
        logger.error("Query failed: " + str(e))
        return None
```

## 延伸資源

詳細的 API 規範與高階用法，參考以下檔案：

- **[技術規範](./references/copilot-instructions-ignition-jython.md)** — 團隊標準與風格指南
- **[Ignition 函數文檔總覽](./references/_index.md)** — 所有 `system.*` 模組索引
- **[Tag 函數參考](./references/ignition-functions-tag.md)** — `system.tag.*` 完整 API
- **[Database 函數參考](./references/ignition-functions-db.md)** — `system.db.*` 與 Named Query 用法
- **[Perspective 函數參考](./references/ignition-functions-perspective.md)** — Web 視覺化開發
- **[通用函數參考](./references/ignition-functions-util.md)** — Logger、非同步呼叫等工具函式
- **[其他模組](./references/_index.md)** — Dataset、Date、Device、File、Net、OPC 等完整模組列表

## 整合工作流程

當使用者請求時，按以下順序進行：

1. **理解需求** — 識別涉及的 `system.*` 模組（Tag、Database、Perspective、Util 等）
2. **查詢規範** — 在[技術規範](./references/copilot-instructions-ignition-jython.md)與 API 參考中確認正確的函數簽名、參數與回傳值
3. **撰寫程式碼** — 依 Jython 2.7 語法產生程式碼，包含完整的 try/except 與 logger
4. **提供說明** — 解釋參數、回傳值、常見坑與測試驗證方式
5. **參考資源** — 在迴應中明確連結到相關 API 文件