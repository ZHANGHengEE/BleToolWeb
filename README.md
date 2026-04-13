# 🚀 Bluetooth Web Assistant (Compact)

一个基于 **Web Bluetooth API** 的网页蓝牙调试工具，专为嵌入式开发与 BLE 调试设计。  
无需安装软件，直接浏览器使用，支持服务浏览、特征读写、通知、HEX/ASCII 数据处理等。

---

## ✨ Features

### 🔌 Connection
- 支持 Chrome / Edge Web Bluetooth
- 支持设备名称前缀过滤（避免“未知设备”）
- 可切换「接受所有设备」
- 自动记录设备列表

---

### 📡 Services & Characteristics
- 所有服务/特征 **平铺显示（不折叠）**
- 支持：
  - ✔ Read
  - ✔ Write / WriteWithoutResponse
  - ✔ Notify / Indicate
- 支持标准服务（180A 等）
- 支持自定义服务（FFF0 / FFF1 / FFF2）

---

### 📊 Data Display
- 自动解析：
  - ASCII
  - HEX
- Notify 实时刷新
- 长数据自动换行（不会撑布局）
- HEX 显示开关

---

### 🛠 Tools
- 选择发送目标特征
- 支持：
  - HEX / ASCII / UTF-8 发送
  - 行结尾控制（LF / CRLF）
- 一键发送

---

### 🧾 Logging
- 全部操作日志记录
- 支持：
  - 时间戳开关
  - HEX 开关
  - 导出日志
- 自动滚动

---

### ⚙️ MTU
- 提供 MTU 设置入口（提示性质）
- ⚠️ 实际 MTU 由系统协商

---

## 🖥 Layout

Left   : Device + Tools (scrollable)  
Middle : Services + Characteristics  
Right  : Logs (wide)

---

## 🚀 Quick Start

### 1️⃣ Run locally

```bash
python -m http.server 8000
```

打开：

```
http://localhost:8000
```

---

### 2️⃣ Connect device

1. 点击 **扫描**
2. 选择设备
3. 自动连接并加载服务

---

### 3️⃣ Debug

- 点击「读」读取数据
- 点击「订阅」接收 Notify
- 实时数据显示在中间 + 日志

---

### 4️⃣ Send data

输入：

```
01 AB E1
```

或：

```
AT+TEST
```

点击发送

---

## ⚠️ Important Notes

### ❗ Web Bluetooth limitations

- 不能持续后台扫描
- MTU 无法强制设置
- 必须用户手动选择设备

---

### ❗ iOS support

- ❌ Safari 不支持
- ✅ Android Chrome 支持

---

## 📂 Project Structure

```
.
├── index.html
└── README.md
```

---

## 🌐 Deploy to GitHub Pages

1. 新建仓库
2. 上传文件
3. Settings → Pages → Deploy

访问：

```
https://yourname.github.io/repo-name/
```

---

## 📄 License

MIT License
