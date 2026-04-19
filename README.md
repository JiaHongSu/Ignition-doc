# Ignition-doc

Ignition 8.1 **系統函數（`system.*`）** 中文參考文件，涵蓋所有內建模組的函數說明、參數定義與使用範例。

---

## 📖 簡介

本專案將 Inductive Automation 官方 Ignition 8.1 腳本 API 整理為 Markdown 格式的中文文件，方便開發人員快速查閱各模組的函數用法，加速開發與維護效率。

---

## 📂 文件結構

| 檔案 | 模組 | 函數數量 | 說明 |
|------|------|---------|------|
| [_index.md](doc/_index.md) | 總覽 | — | 所有模組與函數的索引目錄 |
| [ignition-functions-alarm.md](doc/ignition-functions-alarm.md) | `system.alarm` | 10 | 警報管理（確認、查詢、訂閱等） |
| [ignition-functions-bacnet.md](doc/ignition-functions-bacnet.md) | `system.bacnet` | 7 | BACnet 裝置讀寫操作 |
| [ignition-functions-dataset.md](doc/ignition-functions-dataset.md) | `system.dataset` | 22 | 資料集建立、轉換與操作 |
| [ignition-functions-date.md](doc/ignition-functions-date.md) | `system.date` | 18 | 日期時間格式化、計算與比較 |
| [ignition-functions-db.md](doc/ignition-functions-db.md) | `system.db` | 27 | 資料庫查詢、更新、交易管理 |
| [ignition-functions-device.md](doc/ignition-functions-device.md) | `system.device` | 9 | 裝置連線管理 |
| [ignition-functions-dnp.md](doc/ignition-functions-dnp.md) | `system.dnp` | 12 | DNP 通訊協定操作 |
| [ignition-functions-dnp3.md](doc/ignition-functions-dnp3.md) | `system.dnp3` | 8 | DNP3 通訊協定操作 |
| [ignition-functions-eam.md](doc/ignition-functions-eam.md) | `system.eam` | 4 | 企業管理（EAM）代理程式操作 |
| [ignition-functions-file.md](doc/ignition-functions-file.md) | `system.file` | 8 | 檔案讀寫與目錄操作 |
| [ignition-functions-groups.md](doc/ignition-functions-groups.md) | `system.groups` | 2 | 掃描群組管理 |
| [ignition-functions-gui.md](doc/ignition-functions-gui.md) | `system.gui` | 32 | Vision 視窗、元件與 UI 控制 |
| [ignition-functions-iec61850.md](doc/ignition-functions-iec61850.md) | `system.iec61850` | 7 | IEC 61850 通訊協定操作 |
| [ignition-functions-math.md](doc/ignition-functions-math.md) | `system.math` | 19 | 數學運算函數 |
| [ignition-functions-mongodb.md](doc/ignition-functions-mongodb.md) | `system.mongodb` | 12 | MongoDB 文件查詢與寫入 |
| [ignition-functions-nav.md](doc/ignition-functions-nav.md) | `system.nav` | 12 | Vision 視窗導覽與切換 |
| [ignition-functions-net.md](doc/ignition-functions-net.md) | `system.net` | 11 | HTTP 請求、郵件與網路工具 |
| [ignition-functions-opc.md](doc/ignition-functions-opc.md) | `system.opc` | 11 | OPC-DA 瀏覽與讀寫 |
| [ignition-functions-opchda.md](doc/ignition-functions-opchda.md) | `system.opchda` | 11 | OPC-HDA 歷史資料存取 |
| [ignition-functions-opcua.md](doc/ignition-functions-opcua.md) | `system.opcua` | 3 | OPC-UA 連線與節點操作 |
| [ignition-functions-perspective.md](doc/ignition-functions-perspective.md) | `system.perspective` | 29 | Perspective 工作階段、頁面與元件控制 |
| [ignition-functions-print.md](doc/ignition-functions-print.md) | `system.print` | 5 | 列印視窗與報表 |
| [ignition-functions-project.md](doc/ignition-functions-project.md) | `system.project` | 3 | 專案資源管理 |
| [ignition-functions-report.md](doc/ignition-functions-report.md) | `system.report` | 4 | 報表產生與排程 |
| [ignition-functions-roster.md](doc/ignition-functions-roster.md) | `system.roster` | 7 | 警報通知名單管理 |
| [ignition-functions-secsgem.md](doc/ignition-functions-secsgem.md) | `system.secsgem` | 11 | SECS/GEM 半導體設備通訊 |
| [ignition-functions-security.md](doc/ignition-functions-security.md) | `system.security` | 9 | 使用者驗證與安全區域管理 |
| [ignition-functions-serial.md](doc/ignition-functions-serial.md) | `system.serial` | 11 | 序列埠（RS-232/485）通訊 |
| [ignition-functions-sfc.md](doc/ignition-functions-sfc.md) | `system.sfc` | 9 | 循序功能圖（SFC）流程控制 |
| [ignition-functions-tag.md](doc/ignition-functions-tag.md) | `system.tag` | 26 | Tag 讀寫、瀏覽與歷史查詢 |
| [ignition-functions-twilio.md](doc/ignition-functions-twilio.md) | `system.twilio` | 5 | Twilio 簡訊與語音通知 |
| [ignition-functions-user.md](doc/ignition-functions-user.md) | `system.user` | 27 | 使用者帳號與角色管理 |
| [ignition-functions-util.md](doc/ignition-functions-util.md) | `system.util` | 41 | 通用工具函數（日誌、執行緒、JSON 等） |
| [ignition-functions-vision.md](doc/ignition-functions-vision.md) | `system.vision` | 2 | Vision 客戶端工具 |

> 完整索引請參閱 [_index.md](doc/_index.md)。

---

## 🚀 快速開始

1. 直接瀏覽上方表格，點選對應模組的 Markdown 檔案。
2. 每份文件包含：
   - **函數簽名**（參數型別與回傳值）
   - **參數說明表格**
   - **使用範例**（Python/Jython 腳本）
3. 若需跨模組搜尋，請參閱 [_index.md](doc/_index.md) 的完整函數清單。

---

## 🛠️ 適用版本

- **Ignition 8.1.x**（Inductive Automation）
- 腳本語言：**Jython 2.7**

---

## 📄 授權

本專案採用 [MIT LICENSE](LICENSE) 授權條款，詳情請參閱授權文件。
