# 📱 XMBOX - 强大的Android视频播放器
<div align="center">

![Version](https://img.shields.io/badge/version-3.0.6-blue.svg)
![Android](https://img.shields.io/badge/platform-Android-green.svg)
![License](https://img.shields.io/badge/license-GPL--3.0-orange.svg)
![Build](https://img.shields.io/badge/build-passing-brightgreen.svg)

一个功能强大、界面简洁的Android视频播放器，支持TV和手机双平台。

[下载APK](../../releases) • [功能特性](#-功能特性) • [构建指南](#-构建指南) • [API文档](#-api文档)

</div>

## 🎯 功能特性

### 📺 多平台支持
- **Android TV版本** - 针对电视、盒子优化的遥控器界面
- **手机版本** - 触屏友好的移动端界面
- **多架构支持** - ARM64-V8A 和 ARM V7A 双架构

### 🎬 强大的播放功能
- 🎵 **多格式支持** - 支持主流视频格式播放
- 📡 **直播观看** - 支持各种直播源协议
- 🔍 **智能搜索** - 全局搜索和换源功能
- 📚 **收藏管理** - 视频收藏和历史记录
- 🎨 **自定义界面** - 丰富的主题和布局选项

### ⚡ 技术特色
- 🚀 **高性能播放** - 基于ExoPlayer播放内核
- 🔧 **模块化架构** - 清晰的模块分层设计
- 🛡️ **稳定可靠** - 完善的错误处理和崩溃防护
- 🌐 **网络优化** - 智能代理和DNS解析
- 📱 **Material Design** - 现代化UI设计

## 📥 下载安装

### 最新版本: v3.0.6

| 平台 | ARM64-V8A | ARM V7A |
|------|-----------|---------|
| **📱 手机版** | [下载 (29MB)](../../releases/download/v3.0.6/mobile-arm64_v8a.apk) | [下载 (29MB)](../../releases/download/v3.0.6/mobile-armeabi_v7a.apk) |
| **📺 TV版** | [下载 (27MB)](../../releases/download/v3.0.6/leanback-arm64_v8a.apk) | [下载 (28MB)](../../releases/download/v3.0.6/leanback-armeabi_v7a.apk) |
TV版基于 [FongMi/TV](https://github.com/FongMi/TV) 原项目就改了些配色，想要嘿稳定的可去原项目体验
### 📋 系统要求
- Android 5.0 (API 21) 及以上
- ARM64-V8A: 推荐新设备使用，性能更优
- ARM V7A: 兼容老设备，适配性更强

## 🏗️ 构建指南

### 📋 环境要求
- Android Studio Arctic Fox 或更高版本
- JDK 11 或更高版本
- Android SDK API 35
- Gradle 8.10.2

### 🔧 快速开始

1. **克隆项目**
```bash
git clone https://github.com/yourusername/XMBOX.git
cd XMBOX
```

2. **配置签名** (可选)
```bash
# 将你的签名文件放到 keystore/ 目录
# 或修改 app/build.gradle 中的签名配置
```

3. **构建项目**
```bash
# 构建所有版本
./gradlew assembleRelease

# 构建特定版本
./gradlew assembleMobileArm64_v8aRelease    # 手机版 ARM64
./gradlew assembleLeanbackArm64_v8aRelease  # TV版 ARM64
./gradlew assembleMobileArmeabi_v7aRelease  # 手机版 ARM V7A
./gradlew assembleLeanbackArmeabi_v7aRelease # TV版 ARM V7A
```

4. **生成的APK位置**
```
app/build/outputs/apk/
├── mobileArm64_v8a/release/mobile-arm64_v8a.apk
├── leanbackArm64_v8a/release/leanback-arm64_v8a.apk
├── mobileArmeabi_v7a/release/mobile-armeabi_v7a.apk
└── leanbackArmeabi_v7a/release/leanback-armeabi_v7a.apk
```

## 🏛️ 项目架构

### 📂 模块说明
```
XMBOX/
├── app/                # 主应用模块
│   ├── src/main/      # 通用代码
│   ├── src/mobile/    # 手机版特定代码
│   └── src/leanback/  # TV版特定代码
├── catvod/            # 视频点播核心
├── quickjs/           # JavaScript引擎
├── forcetech/         # 强制技术模块
├── thunder/           # 迅雷下载模块
├── hook/              # 钩子功能
├── jianpian/          # 视频剪辑模块
├── tvbus/             # TV总线功能
└── zlive/             # 直播功能模块
```

### 🔧 技术栈
- **开发语言**: Java
- **UI框架**: Android Views + Material Components
- **播放器**: ExoPlayer
- **网络库**: OkHttp
- **JSON解析**: Gson
- **异步处理**: EventBus
- **数据库**: Room

## 📝 更新日志

### v3.0.5 (2025-08-20)
#### 🎨 界面优化
- 优化导航栏历史记录图标，采用 Material Design 3 规范的列表图标
- 改进设置页面的图标显示效果
- 优化用户界面视觉体验

### v3.0.4 (2025-07-30)
#### 🐛 修复
- 修复设置页面源管理模块中切换视频源时的随机闪退问题
- 增强VodConfig.setHome()方法的空指针异常处理
- 改进Fragment生命周期检查以防止崩溃
- 优化HistoryDialog中源切换的安全性
- 增强并发加载的线程安全性

#### ⚡ 优化
- 提升应用启动速度
- 优化内存使用
- 增强网络请求稳定性

#### 🆕 新增
- 新增自动缓存清理功能
- 添加更完善的错误处理机制
- 增强崩溃保护功能

### v3.0.3 及更早版本
查看 [完整更新日志](CHANGELOG.md)

## 🔌 API 文档

### 刷新操作
```http
# 刷新详情
GET http://127.0.0.1:9978/action?do=refresh&type=detail

# 刷新播放
GET http://127.0.0.1:9978/action?do=refresh&type=player

# 刷新直播
GET http://127.0.0.1:9978/action?do=refresh&type=live
```

### 推送功能
```http
# 推送字幕
GET http://127.0.0.1:9978/action?do=refresh&type=subtitle&path=http://xxx

# 推送弹幕
GET http://127.0.0.1:9978/action?do=refresh&type=danmaku&path=http://xxx
```

### 缓存管理
```http
# 新增缓存
GET http://127.0.0.1:9978/cache?do=set&key=xxx&value=xxx

# 获取缓存
GET http://127.0.0.1:9978/cache?do=get&key=xxx

# 删除缓存
GET http://127.0.0.1:9978/cache?do=del&key=xxx
```

更多API文档请查看 [API参考手册](docs/API.md)

## 📖 配置说明

### 点播字段配置
| 字段名 | 默认值 | 说明 | 备注 |
|--------|--------|------|------|
| searchable | 1 | 是否支持搜索 | 0:关闭 1:启用 |
| changeable | 1 | 是否支持换源 | 0:关闭 1:启用 |
| quickSearch | 1 | 是否快速搜索 | 0:关闭 1:启用 |
| timeout | 15 | 播放超时时间 | 单位:秒 |

### 直播字段配置
| 字段名 | 默认值 | 说明 | 备注 |
|--------|--------|------|------|
| ua | none | 用户代理 | |
| origin | none | 来源 | |
| referer | none | 引用地址 | |
| timeout | 15 | 播放超时 | 单位:秒 |

详细配置说明请查看 [配置文档](docs/CONFIG.md)

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

### 🔄 提交规范
- feat: 新功能
- fix: 修复bug
- docs: 文档更新
- style: 代码格式调整
- refactor: 代码重构
- test: 测试相关
- chore: 构建配置等

### 🧪 开发流程
1. Fork 本项目
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建 Pull Request

## ⚖️ 免责声明

1. **学习用途**: 本项目仅供学习和技术交流使用，不得用于商业用途
2. **内容来源**: 项目中的内容来源于网络，如有侵权请联系删除
3. **使用责任**: 使用本项目产生的一切后果由使用者自行承担
4. **法律合规**: 请确保在当地法律法规允许的范围内使用本软件

## 📄 开源协议

本项目基于 [GPL-3.0](LICENSE.md) 协议开源

## 🙏 致谢

- 基于 [FongMi/TV](https://github.com/FongMi/TV) 项目开发
- 感谢 [CatVodTVOfficial](https://github.com/CatVodTVOfficial) 提供的核心技术
- 感谢所有为项目做出贡献的开发者

## 📞 联系方式

- GitHub Issues: [提交问题](../../issues)
- 讨论区: [Discussions](../../discussions)

---

<div align="center">

**⭐ 如果这个项目对你有帮助，请给我们一个 Star！**

Made with ❤️ by XMBOX Team

</div>
