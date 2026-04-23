# Ignition 知識庫索引

本檔案用於 GitHub Copilot 快速定位相關文件。

## 模組導覽

### 資料操作

- **Tag 讀寫** → `doc/ignition-functions-tag.md` - 26 函數
- **資料集** → `doc/ignition-functions-dataset.md` - 22 函數
- **資料庫** → `doc/ignition-functions-db.md` - 27 函數
- **日期時間** → `doc/ignition-functions-date.md` - 18 函數

### UI 視覺化

- **Vision** → `doc/ignition-functions-vision.md`
- **Perspective** → `doc/ignition-functions-perspective.md` - 29 函數
- **GUI 控制** → `doc/ignition-functions-gui.md` - 32 函數
- **導覽管理** → `doc/ignition-functions-nav.md` - 12 函數

### 通訊協定

- **OPC-UA** → `doc/ignition-functions-opcua.md` - 3 函數
- **OPC-HDA** → `doc/ignition-functions-opchda.md` - 11 函數
- **OPC-DA** → `doc/ignition-functions-opc.md` - 11 函數
- **BACnet** → `doc/ignition-functions-bacnet.md` - 7 函數
- **DNP3** → `doc/ignition-functions-dnp3.md` - 8 函數
- **DNP** → `doc/ignition-functions-dnp.md` - 12 函數
- **IEC 61850** → `doc/ignition-functions-iec61850.md` - 7 函數
- **SECS/GEM** → `doc/ignition-functions-secsgem.md` - 11 函數

### 硬體/連接

- **裝置管理** → `doc/ignition-functions-device.md` - 9 函數
- **序列埠** → `doc/ignition-functions-serial.md` - 11 函數

### 通知/報表

- **警報** → `doc/ignition-functions-alarm.md` - 10 函數
- **報表** → `doc/ignition-functions-report.md` - 4 函數
- **列印** → `doc/ignition-functions-print.md` - 5 函數
- **Twilio（簡訊）** → `doc/ignition-functions-twilio.md` - 5 函數

### 系統管理

- **使用者/安全** → `doc/ignition-functions-security.md` - 9 函數
- **使用者帳號** → `doc/ignition-functions-user.md` - 27 函數
- **掃描群組** → `doc/ignition-functions-groups.md` - 2 函數
- **專案資源** → `doc/ignition-functions-project.md` - 3 函數
- **企業管理** → `doc/ignition-functions-eam.md` - 4 函數

### 工具類

- **通用工具** → `doc/ignition-functions-util.md` - 41 函數
- **檔案操作** → `doc/ignition-functions-file.md` - 8 函數
- **數學運算** → `doc/ignition-functions-math.md` - 19 函數
- **網路操作** → `doc/ignition-functions-net.md` - 11 函數
- **MongoDB** → `doc/ignition-functions-mongodb.md` - 12 函數
- **SFC** → `doc/ignition-functions-sfc.md` - 9 函數

### 其他

- **警報通知** → `doc/ignition-functions-roster.md` - 7 函數

---

## 查詢方式

**使用者詢問時的匹配規則：**

| 關鍵字                    | 對應檔案                                  |
| ------------------------- | ----------------------------------------- |
| `system.tag`              | ignition-functions-tag.md                 |
| `system.db` 或 `database` | ignition-functions-db.md                  |
| `system.perspective`      | ignition-functions-perspective.md         |
| `system.gui` 或 Vision UI | ignition-functions-gui.md                 |
| `system.util`             | ignition-functions-util.md                |
| `OPC` 或 `OPC-UA`         | ignition-functions-opcua.md               |
| `dataset`                 | ignition-functions-dataset.md             |
| `user` 或 `security`      | ignition-functions-user.md 或 security.md |
| `alarm`                   | ignition-functions-alarm.md               |
| `report`                  | ignition-functions-report.md              |

---

## 指示原則

1. **優先查詢** 本知識庫中的對應 `.md` 檔
2. **完整命名空間** - 必須使用 `system.module.function()` 格式
3. **Jython 2.7** - 禁止 f-string、必須用 `try/except`
4. **Perspective > Vision** - 預設推薦 Perspective
5. **超出範圍** - 指向官方 Ignition 文件
