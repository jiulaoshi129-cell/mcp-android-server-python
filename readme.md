MCP Android Agent

!Python 3.13 !MCP !License: MIT

MCP Android Agent 是一个基于 Python、MCP（Model Context Protocol）和 uiautomator2 开发的 Android 自动化控制服务器。

通过 MCP 协议，可以将 Android 手机或模拟器接入 AI Agent，例如 Claude Desktop、GitHub Copilot 和 VS Code Agent，实现通过自然语言控制 Android 设备。

✨ 核心功能
1. 设备管理
自动检测和连接 Android 设备
获取设备型号、Android 版本及屏幕分辨率
获取电池状态和设备信息
检查 ADB 连接状态
2. 应用管理
获取已安装应用列表
启动、停止和强制关闭应用
获取当前前台应用信息
清除应用数据和缓存
3. 屏幕控制
打开和关闭屏幕
自动解锁设备
等待屏幕状态变化
4. 自动化操作
点击指定文本或 UI 元素
长按、滑动和拖动
自动输入文本
模拟 Home、Back、Menu 等硬件按键
5. UI 检查与调试
获取 UI 元素详细信息
导出完整 UI 层级 XML
获取设备截图
等待指定元素出现
自动滚动查找目标元素
6. 高级功能
获取 Android Toast 消息
等待指定 Activity 启动
支持异步操作
🏗️ 项目架构
text
mcp-android-server-python/
│
├── server.py
├── server_original_backup.py
│
└── tools/
    ├── __init__.py
    ├── device_tools.py
    ├── app_tools.py
    ├── screen_tools.py
    ├── input_tools.py
    ├── inspection_tools.py
    └── advanced_tools.py


采用模块化设计，将不同功能独立管理，方便维护、测试和扩展。

🛠️ 技术栈
技术	用途
Python 3.13+	核心开发语言
MCP	AI Agent 与 Android 设备通信
FastMCP	MCP Server 实现
uiautomator2	Android UI 自动化
ADB	Android 设备连接与管理
uv	Python 环境和依赖管理
📋 环境要求
Python 3.13 或更高版本
Android SDK Platform Tools
ADB 已配置到系统 PATH
Android 真机或兼容模拟器
Android 设备已开启 USB 调试
🚀 快速安装
1. 克隆项目
bash
git clone https://github.com/nim444/mcp-android.git

cd mcp-android

2. 创建虚拟环境
bash
uv venv --python 3.13


激活环境：

Windows：

powershell
.venv\Scripts\activate


Linux / macOS：

bash
source .venv/bin/activate

3. 安装依赖
bash
uv pip install

4. 检查 Android 设备
bash
adb devices

5. 初始化 uiautomator2
bash
python -m uiautomator2 init

6. 启动 MCP Server
bash
uv run python server.py


支持两种通信模式：

stdio：适用于 Claude Desktop、VS Code 等 MCP 客户端。
Streamable HTTP：适用于 Web 应用和 HTTP 客户端。

具体启动配置以 server.py 为准。

🤖 AI Agent 集成

支持接入：

Claude Desktop
VS Code Agent
GitHub Copilot Chat
其他兼容 MCP 协议的 AI Agent

配置完成后，可以直接通过自然语言执行 Android 自动化操作。

例如：

text
获取当前 Android 设备信息。

打开手机上的设置应用。

查看当前屏幕的 UI 元素。

点击 Wi-Fi 设置。

获取当前屏幕截图。

🎯 应用场景
Android 自动化测试
AI 驱动的手机操作
移动应用 UI 测试
自动化 QA 测试
Android 设备管理
智能 Agent 与移动设备集成
🔒 安全说明
建议仅连接可信任的 Android 设备。
HTTP 模式应配置适当的访问控制。
不要将未授权的 ADB 或 MCP 服务暴露到公网。
自动化操作前应确认设备和目标应用。
📄 License

本项目采用 MIT License 开源协议。

MCP Android Agent — Connect AI Agents with Android Devices.
