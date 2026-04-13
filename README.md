🚀 Bluetooth Web Assistant（紧凑版）

一个基于 Web Bluetooth API 的轻量级蓝牙调试工具，专为工程开发设计，支持服务/特征浏览、读写、通知、HEX/ASCII 数据处理等功能。

✨ 功能特点
🔌 蓝牙连接
支持 Web Bluetooth（Chrome / Edge）
默认按设备名称前缀过滤（避免大量“未知设备”）
支持手动开启“接受所有设备”
自动记录设备并按信号强度排序
📡 服务 & 特征（核心）
所有 Service / Characteristic 平铺显示（不折叠）
支持：
Read（读）
Write / WriteWithoutResponse（写）
Notify / Indicate（通知）
自动识别常见标准 UUID（如 180A / 2A24 等）
支持自定义服务（如 FFF0 / FFF1 / FFF2）
📊 数据显示
自动解析：
ASCII
HEX
实时 Notify 数据刷新
长数据自动换行，不撑布局
支持 HEX 显示开关
🛠 工具区
选择发送目标特征
支持：
HEX / ASCII / UTF-8 发送
行结尾控制（LF / CRLF）
一键发送数据
🧾 日志系统
所有操作日志记录
支持：
时间戳开关
HEX 显示
导出日志（txt）
自动滚动
⚙️ MTU
提供 MTU 设置入口（提示性质）
⚠️ Web Bluetooth 实际 MTU 由系统决定
🖥 界面布局（工程优化）
左侧：设备 + 工具（可滚动）
中间：服务 + 特征（紧凑）
右侧：日志（宽显示）

特点：

单屏显示（无需折叠）
高密度信息展示
适合调试使用
🧪 使用方法
1️⃣ 打开方式

必须满足：

Chrome / Edge 浏览器
HTTPS 或 localhost

👉 推荐：

# 方法1：直接本地
python -m http.server 8000

打开：

http://localhost:8000
2️⃣ 连接设备
点击【扫描】
选择设备（默认过滤 CityU_）
自动连接并加载服务
3️⃣ 调试流程
查看服务 → 找到特征（如 FFF1）
点击：
【读】
【订阅】
数据实时显示
4️⃣ 发送数据
选择目标特征（如 FFF2）

输入数据：

01 AB E1

或

AT+TEST
点击【发送】
⚠️ 注意事项
❗1. Web Bluetooth 限制
无法像手机 App 一样持续扫描
无法获取真实 RSSI（此处为模拟排序）
MTU 不可强制设置
需用户手动选择设备
❗2. 未知设备问题

浏览器弹窗中：

未知或不支持的设备

👉 原因：

未广播名称
未匹配过滤规则

✅ 本工具解决方案：

默认使用 namePrefix 过滤（如 CityU_）
❗3. iOS 支持
❌ Safari 不支持 Web Bluetooth
✅ Android Chrome 支持
🧩 项目结构
.
├── bluetooth_web_assistant.html
└── README.md
🚀 部署（GitHub Pages）
上传 HTML 文件
Settings → Pages
选择 main 分支
访问：
https://yourname.github.io/project/
🔥 可扩展方向（推荐）

后续可以升级：

✔ 可拖拽分栏（VSCode风格）
✔ HEX / ASCII 切换按钮（特征内）
✔ 数据流高亮（类似示波器）
✔ 自动重连
✔ 多设备支持
✔ BLE吞吐优化（10Hz+）
👨‍💻 适用场景
BLE设备调试
嵌入式开发（CH32 / STM32 / Nordic）
自定义协议分析
数据链路测试
📄 License

MIT License

💬 作者说明

这是一个工程导向工具，目标是：

👉 替代手机蓝牙助手
👉 提供更高密度调试界面
👉 支持自定义协议开发

如果你要，我可以再帮你做一个👇

👉 README + GitHub 封面图（类似开源项目）
👉 或直接帮你做成一个“可发布项目结构” 😎
