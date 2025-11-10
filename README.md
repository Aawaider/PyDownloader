# PyDownloader Pro - 专业下载管理器

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-GNU-green.svg)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)
![Version](https://img.shields.io/badge/Version-Alpha1-orange.svg)

## 🚀 项目简介

PyDownloader Pro 是一款功能强大的专业下载管理器，采用 Python 和 Tkinter 开发，具备现代化的用户界面和丰富的功能特性。支持普通文件下载和多种网盘链接解析，为用户提供一站式下载解决方案。

## ✨ 核心特性

### 🎯 下载管理
- **多线程下载**：支持 1-16 线程并发下载，大幅提升下载速度
- **断点续传**：自动保存下载进度，支持任务恢复
- **实时监控**：实时显示下载速度、进度和剩余时间
- **任务管理**：支持暂停、继续、取消等操作
- **批量下载**：支持多个URL批量添加下载

### ☁️ 网盘支持
- **全平台支持**：百度网盘、阿里云盘、蓝奏云、腾讯微云、夸克网盘等
- **智能解析**：自动识别网盘链接类型，提取文件列表
- **批量选择**：多文件选择界面，支持全选和批量下载
- **通用解析**：智能识别其他网盘链接，提供通用解析方案

### 💾 数据持久化
- **自动保存**：配置、历史记录、活动任务自动保存
- **任务恢复**：程序重启后自动恢复未完成的任务
- **历史管理**：完整的下载历史记录，支持查看和导出
- **配置管理**：用户设置持久化保存

### 🎨 用户界面
- **现代化设计**：深色主题，美观易用
- **实时日志**：详细的下载操作日志
- **状态监控**：实时显示下载状态和系统信息
- **批量操作**：支持批量添加和管理下载任务

## 🔗相关链接
**开源地址**:https://github.com/Aawaider/PyDownloader

**Alpha1下载链接**:[Github下载](https://github.com/Aawaider/PyDownloader/releases/tag/Alpha1)，[百度网盘下载](https://pan.baidu.com/s/1OdiP7FerD_1Co5x9zZJ-UQ?pwd=jp76)，[123网盘下载](https://www.123865.com/s/uMdgvd-lyWc3)

**Alpha2下载链接**:[Github下载](https://github.com/Aawaider/PyDownloader/releases/tag/Alpha2)，[百度网盘下载](https://pan.baidu.com/s/1Ql1UY4VplZ--Hk-_j2qMTw?pwd=7nm3)，[123网盘下载](https://www.123865.com/s/uMdgvd-mVWc3)

## 📦 安装说明（仅针对于直接克隆仓库的用户）

### 环境要求
- Python 3.8 或更高版本
- 支持的操作系统：Windows、Linux、macOS

### 安装依赖
```bash
pip install requests beautifulsoup4
```

### 运行程序
```bash
python PyDownloader.py
```

## 🛠 使用指南

### 普通下载
1.在URL输入框中粘贴文件直链

2.设置下载线程数和保存路径

3.点击"新建下载"开始下载

### 网盘下载
1.粘贴网盘分享链接

2.点击"解析网盘"按钮

3.在弹出窗口中选择要下载的文件

3.点击"开始下载"添加到下载队列

### 批量操作
1.批量下载：点击"批量下载"，输入多个URL（每行一个）

2.批量管理：在下载列表中选择多个任务进行暂停、继续或取消操作

### 数据管理

1.查看历史：点击"下载历史"查看所有下载记录

2.导出记录：支持将历史记录导出为JSON格式

3.清理记录：一键清空下载历史记录

4.恢复任务：点击"恢复任务"重新开始未完成的下载

## 🏗 技术架构
### 核心模块
``` text
PyDownloader Pro/
├── 用户界面层 (Tkinter)
│   ├── 主窗口管理
│   ├── 任务列表显示
│   └── 实时日志系统
├── 业务逻辑层
│   ├── 下载引擎
│   ├── 网盘解析器
│   └── 任务调度器
└── 数据持久层
    ├── 配置管理
    ├── 历史记录
    └── 任务状态
```
### 网盘解析架构
智能检测：基于正则表达式的链接类型识别

多策略解析：使用BeautifulSoup分析网页结构

容错机制：解析失败时提供模拟数据保证功能正常

通用适配：支持未知网盘链接的通用解析

## 🔧 配置说明
### 默认配置
```json
{
    "max_threads": 8,
    "chunk_size": 8192,
    "timeout": 30,
    "retry_count": 3,
    "download_path": "~/Downloads"
}
```
### 配置文件位置
Windows：`C:\Users\<用户名>\.pydownloader_pro\`

Macos/Liunx：`~/.pydownloader_pro/`

包含的文件:

`config.json` - 程序配置

`download_history.json` - 下载历史记录

`active_tasks.json` - 活动任务状态

<img width="767" height="517" alt="image" src="https://github.com/user-attachments/assets/1f20877f-42c7-479a-81a5-b17016dce407" />

## 🐛 故障排除

### 常见问题
**Q: 程序启动时报错 "No module named 'requests'"**

运行下面的即可.
```bash
# 解决方案
pip install requests beautifulsoup4
```

**Q: 网盘解析失败或显示模拟数据**

- 检查网络连接是否正常

- 确认链接格式正确

- 尝试使用其他网盘链接

- 查看日志获取详细错误信息

**Q: 下载速度慢**

- 尝试增加线程数（设置中调整）

- 检查网络带宽状况

- 确认目标服务器状态

- 尝试暂停后重新开始下载

**Q: 任务无法恢复或数据丢失**

- 检查数据目录写入权限

- 确认磁盘空间充足

- 查看日志文件中的错误信息

- 尝试手动恢复任务

### 日志查看
**程序运行日志实时显示在界面底部的日志区域，包含：**

- 操作记录

- 错误信息

- 下载状态

- 网络请求详情

## 🔄 更新日志
### Alpha2（当前版本）
✅所有网盘均可解析。

✅网盘解析出来的不再是模拟文件啦。

### Alpha1 
✅ 全平台网盘支持（8大主流网盘）

✅ 智能链接解析引擎

✅ 多线程下载优化（1-16线程）

✅ 完整数据持久化存储

✅ 现代化深色主题界面

✅ 实时日志监控系统

## 🤝 贡献指南

我们欢迎社区贡献！如果您想为项目做出贡献，请：

**1.Fork 本项目**

**2.创建特性分支**
```bash
git checkout -b feature/AmazingFeature
```

**3.提交更改**
```bash
git commit -m 'Add some AmazingFeature'
```

**4.推送到分支**
```bash
git push origin feature/AmazingFeature
```

**5.开启 Pull Request**

### 开发环境设置
```bash
# 克隆项目
git clone https://github.com/Aawaider/PyDownloader.git

# 进入目录
cd PyDownloader

# 安装开发依赖
pip install requests beautifulsoup4
```

## 📄 许可证

本项目采用 GNU 许可证 - 查看 LICENSE 文件了解详情。

## 📞联系我们
Email：m.fialiaoi9363@outlook.com

电话:18049679363（挂断就是作者在上课）

## 🙏 致谢
**感谢所有为这个项目做出贡献的开发者**：

- Python官网 - 提供Python编译器

- 测试人员 - 提供宝贵的反馈和建议

- 开源社区 - 提供的优秀库和工具

- 用户群体 - 持续的支持与使用反馈

**特别感谢以下开源项目**：

- Requests - HTTP库

- Beautiful Soup - HTML解析

- Tkinter - GUI框架

<div align="center">
PyDownloader Pro - 让下载更简单、更高效！ 🚀

如果这个项目对您有帮助，请给个 ⭐️ 支持一下！

</div>
