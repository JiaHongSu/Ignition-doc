# Ignition-doc

A Chinese reference documentation for Ignition 8.1 **system functions (`system.*`)**, covering function descriptions, parameter definitions, and usage examples for all built-in modules.

---

## 📖 Introduction

This project organizes the official Inductive Automation Ignition 8.1 scripting API into Markdown-formatted Chinese documentation, allowing developers to quickly look up function usage across modules and improve development and maintenance efficiency.

---

## 📂 Document Structure

| File | Module | Functions | Description |
|------|--------|-----------|-------------|
| [_index.md](doc/_index.md) | Index | — | Full index of all modules and functions |
| [ignition-functions-alarm.md](doc/ignition-functions-alarm.md) | `system.alarm` | 10 | Alarm management (acknowledge, query, subscribe, etc.) |
| [ignition-functions-bacnet.md](doc/ignition-functions-bacnet.md) | `system.bacnet` | 7 | BACnet device read/write operations |
| [ignition-functions-dataset.md](doc/ignition-functions-dataset.md) | `system.dataset` | 22 | Dataset creation, conversion, and manipulation |
| [ignition-functions-date.md](doc/ignition-functions-date.md) | `system.date` | 18 | Date/time formatting, calculation, and comparison |
| [ignition-functions-db.md](doc/ignition-functions-db.md) | `system.db` | 27 | Database queries, updates, and transaction management |
| [ignition-functions-device.md](doc/ignition-functions-device.md) | `system.device` | 9 | Device connection management |
| [ignition-functions-dnp.md](doc/ignition-functions-dnp.md) | `system.dnp` | 12 | DNP protocol operations |
| [ignition-functions-dnp3.md](doc/ignition-functions-dnp3.md) | `system.dnp3` | 8 | DNP3 protocol operations |
| [ignition-functions-eam.md](doc/ignition-functions-eam.md) | `system.eam` | 4 | Enterprise Administration Manager (EAM) agent operations |
| [ignition-functions-file.md](doc/ignition-functions-file.md) | `system.file` | 8 | File read/write and directory operations |
| [ignition-functions-groups.md](doc/ignition-functions-groups.md) | `system.groups` | 2 | Scan group management |
| [ignition-functions-gui.md](doc/ignition-functions-gui.md) | `system.gui` | 32 | Vision windows, components, and UI control |
| [ignition-functions-iec61850.md](doc/ignition-functions-iec61850.md) | `system.iec61850` | 7 | IEC 61850 protocol operations |
| [ignition-functions-math.md](doc/ignition-functions-math.md) | `system.math` | 19 | Mathematical functions |
| [ignition-functions-mongodb.md](doc/ignition-functions-mongodb.md) | `system.mongodb` | 12 | MongoDB document queries and writes |
| [ignition-functions-nav.md](doc/ignition-functions-nav.md) | `system.nav` | 12 | Vision window navigation and switching |
| [ignition-functions-net.md](doc/ignition-functions-net.md) | `system.net` | 11 | HTTP requests, email, and networking utilities |
| [ignition-functions-opc.md](doc/ignition-functions-opc.md) | `system.opc` | 11 | OPC-DA browsing and read/write |
| [ignition-functions-opchda.md](doc/ignition-functions-opchda.md) | `system.opchda` | 11 | OPC-HDA historical data access |
| [ignition-functions-opcua.md](doc/ignition-functions-opcua.md) | `system.opcua` | 3 | OPC-UA connection and node operations |
| [ignition-functions-perspective.md](doc/ignition-functions-perspective.md) | `system.perspective` | 29 | Perspective session, page, and component control |
| [ignition-functions-print.md](doc/ignition-functions-print.md) | `system.print` | 5 | Printing windows and reports |
| [ignition-functions-project.md](doc/ignition-functions-project.md) | `system.project` | 3 | Project resource management |
| [ignition-functions-report.md](doc/ignition-functions-report.md) | `system.report` | 4 | Report generation and scheduling |
| [ignition-functions-roster.md](doc/ignition-functions-roster.md) | `system.roster` | 7 | Alarm notification roster management |
| [ignition-functions-secsgem.md](doc/ignition-functions-secsgem.md) | `system.secsgem` | 11 | SECS/GEM semiconductor equipment communication |
| [ignition-functions-security.md](doc/ignition-functions-security.md) | `system.security` | 9 | User authentication and security zone management |
| [ignition-functions-serial.md](doc/ignition-functions-serial.md) | `system.serial` | 11 | Serial port (RS-232/485) communication |
| [ignition-functions-sfc.md](doc/ignition-functions-sfc.md) | `system.sfc` | 9 | Sequential Function Chart (SFC) flow control |
| [ignition-functions-tag.md](doc/ignition-functions-tag.md) | `system.tag` | 26 | Tag read/write, browsing, and history queries |
| [ignition-functions-twilio.md](doc/ignition-functions-twilio.md) | `system.twilio` | 5 | Twilio SMS and voice notifications |
| [ignition-functions-user.md](doc/ignition-functions-user.md) | `system.user` | 27 | User account and role management |
| [ignition-functions-util.md](doc/ignition-functions-util.md) | `system.util` | 41 | General utility functions (logging, threading, JSON, etc.) |
| [ignition-functions-vision.md](doc/ignition-functions-vision.md) | `system.vision` | 2 | Vision client utilities |

> For the full index, see [_index.md](doc/_index.md).

---

## 🚀 Getting Started

1. Browse the table above and click the Markdown file for the module you need.
2. Each document contains:
   - **Function signature** (parameter types and return values)
   - **Parameter description table**
   - **Usage examples** (Python/Jython scripts)
3. For cross-module search, refer to the complete function list in [_index.md](doc/_index.md).

---

## 🛠️ Supported Version

- **Ignition 8.1.x** (Inductive Automation)
- Scripting language: **Jython 2.7**

---

## 📄 License

This project is licensed under the [MIT LICENSE](LICENSE). See the license file for details.
