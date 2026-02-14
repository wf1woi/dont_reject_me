# 💕 别拒绝TA - 趣味表白页面

[English](./README_EN.md) | 中文

一个有趣的单页表白应用，用户尝试点击"同意"按钮时，"拒绝"按钮会躲避、逃跑、分身，带来有趣的互动体验。

![Preview](https://img.shields.io/badge/Preview-Live%20Demo-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

## ✨ 功能特性

### 🎮 核心玩法
- **拒绝按钮会躲避** - 鼠标靠近时按钮会自动逃离，无法轻易点击
- **渐进式趣味** - 拒绝次数越多，趣味效果越丰富
- **分身特效** - 多次拒绝后会出现多个伪装的拒绝按钮
- **伪装机制** - 分身按钮平时显示"拒绝"，鼠标靠近时变成"同意"

### 🎨 视觉特效
| 特效 | 描述 |
|------|------|
| 💗 爱心 | 飘落的爱心动画 |
| ⭐ 星星 | 闪烁的星星背景 |
| 🎊 彩带 | 庆祝时的彩带爆炸 |
| 🫧 气泡 | 浪漫的气泡上升 |
| ❄️ 雪花 | 飘落的雪花 |
| 🌸 花瓣 | 飘落的花瓣 |
| ☄️ 流星 | 划过的流星 |
| 🎆 烟花 | 盛大的烟花表演 |
| 🌈 彩虹 | 彩虹背景 |
| ⚡ 闪电 | 闪电效果 |

### ⚙️ 触发特效（达到拒绝次数后激活）
| 特效 | 描述 |
|------|------|
| 🔄 摇晃 | 拒绝按钮左右摇晃 |
| 🔊 音效 | 播放有趣的声音 |
| 😢 哭泣 | 显示哭泣表情 |
| 🏃 逃跑 | 按钮快速逃跑 |
| 👥 分身 | 生成多个假按钮 |
| 🎨 反色 | 按钮颜色反转 |

### 📝 配置选项
- 自定义问题和按钮文字
- 自定义成功页面文案
- 个性化提示语（支持 {attempts} 变量）
- 主题颜色自定义
- 选择开启/关闭各项特效
- 调整触发特效的拒绝次数阈值
- 设置躲避检测范围 (50-300px)
- 显示/隐藏配置中心链接

## 🚀 快速开始

### 方式一：直接使用（推荐）

点击即可开始使用：https://wf1woi.github.io/dont_reject_me

1. 访问 [配置中心](https://wf1woi.github.io/dont_reject_me/admin)
2. 自定义你的表白内容
3. 点击"生成分享链接"按钮
4. 将生成的链接发给TA

### 方式二：自部署

#### Vercel / Netlify 部署

1. Fork 本仓库
2. 在 Vercel 或 Netlify 中导入项目
3. 自动部署完成
4. 访问生成的域名

#### GitHub Pages 部署

1. Fork 本仓库
2. 进入 Settings → Pages
3. Source 选择 "Deploy from a branch"
4. Branch 选择 "main"，目录选择 "/ (root)"
5. 点击 Save，等待部署完成

#### 本地运行

```bash
# 克隆仓库
git clone https://github.com/你的用户名/dont-reject-me.git
cd dont-reject-me

# 方式一：使用 Python 启动服务器（推荐）
python -m http.server 8080
# 然后访问 http://localhost:8080

# 方式二：使用 Node.js
npx http-server -p 8080

# 方式三：直接用浏览器打开 HTML 文件（无需服务器）
# 直接双击 index.html 即可在浏览器中打开
```

> 💡 **为什么需要 HTTP 服务器？**
> 虽然可以直接双击打开 HTML 文件，但通过服务器访问可以：
> - 正确加载 URL 参数（如分享的配置链接 `?c=xxx`）
> - 模拟真实的线上部署环境
> - 某些浏览器功能（如 localStorage）在 file:// 协议下可能受限

## 📁 项目结构

```
dont-reject-me/
├── index.html      # 主页面（表白页面）
├── admin.html     # 配置中心（自定义内容）
└── README.md      # 项目文档
```

## 🔧 工作原理

### 躲避逻辑
```javascript
// 鼠标靠近时计算距离
const distance = Math.hypot(mouseX - btnX, mouseY - btnY);

// 当距离小于检测范围时触发躲避
if (distance < avoidDistance) {
    moveButtonToRandomPosition();
}
```

### 配置分享
配置通过 URL 参数传递，使用 LZString 压缩 + 短键名优化 URL 长度：
```
https://domain.com/index.html?c=N4IgjiBc...
```

### 渐进式趣味
```javascript
// 根据拒绝次数增加趣味等级
const level = Math.min(5, Math.floor((attempts - triggerCount) / 3) + 1);
triggerSpecialEffects(level);
```

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/xxx`)
3. 提交更改 (`git commit -m 'Add xxx'`)
4. 推送分支 (`git push origin feature/xxx`)
5. 创建 Pull Request

## 📄 许可证

MIT License - 自由使用和修改

---

Made with ❤️ for fun confessions
