# 💕 Don't Reject Me - Fun Confession Page

[English](./README_EN.md) | [中文](./README.md)

A fun single-page confession app where the "Reject" button runs away, escapes, and multiplies when the user tries to click "Accept", creating an entertaining interactive experience.

![Preview](https://img.shields.io/badge/Preview-Live%20Demo-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

## ✨ Features

### 🎮 Core Gameplay
- **Reject button runs away** - The button automatically flees when the mouse approaches, making it hard to click
- **Progressive fun** - The more times you reject, the more interesting the effects become
- **Clone effect** - Multiple fake reject buttons appear after multiple rejections
- **Disguise mechanism** - Clone buttons show "Reject" normally, but transform into "Accept" when mouse approaches

### 🎨 Visual Effects
| Effect | Description |
|--------|-------------|
| 💗 Hearts | Falling heart animations |
| ⭐ Stars | Twinkling star background |
| 🎊 Confetti | Celebration confetti explosion |
| 🫧 Bubbles | Romantic rising bubbles |
| ❄️ Snow | Falling snowflakes |
| 🌸 Petals | Falling flower petals |
| ☄️ Meteor | Shooting meteors |
| 🎆 Fireworks | Grand fireworks display |
| 🌈 Rainbow | Rainbow background |
| ⚡ Lightning | Lightning effects |

### ⚙️ Trigger Effects (Activated after rejection threshold)
| Effect | Description |
|--------|-------------|
| 🔄 Shake | Reject button shakes left and right |
| 🔊 Sound | Play fun sounds |
| 😢 Cry | Display crying expression |
| 🏃 Runaway | Button runs away quickly |
| 👥 Clone | Generate multiple fake buttons |
| 🎨 Invert | Button color inversion |

### 📝 Configuration Options
- Custom question and button text
- Custom success page message
- Personalized hints (supports {attempts} variable)
- Custom theme colors
- Toggle effects on/off
- Adjust rejection count threshold for trigger effects
- Set avoidance detection range (50-300px)
- Show/hide configuration center link

## 🚀 Quick Start

### Method 1: Direct Use (Recommended)

Click to start: https://wf1woi.github.io/dont_reject_me

1. Visit [Configuration Center](https://wf1woi.github.io/dont_reject_me/admin)
2. Customize your confession content
3. Click "Generate Share Link" button
4. Send the generated link to your crush

### Method 2: Self-Deploy

#### Vercel / Netlify Deployment

1. Fork this repository
2. Import project in Vercel or Netlify
3. Automatic deployment complete
4. Visit the generated domain

#### GitHub Pages Deployment

1. Fork this repository
2. Go to Settings → Pages
3. Source: Select "Deploy from a branch"
4. Branch: Select "main", directory: "/ (root)"
5. Click Save, wait for deployment

#### Local Development

```bash
# Clone repository
git clone https://github.com/your-username/dont-reject-me.git
cd dont-reject-me

# Method 1: Using Python (Recommended)
python -m http.server 8080
# Then visit http://localhost:8080

# Method 2: Using Node.js
npx http-server -p 8080

# Method 3: Open directly in browser (no server needed)
# Just double-click index.html to open in browser
```

> 💡 **Why need an HTTP server?**
> Although you can open HTML files directly by double-clicking, using a server ensures:
> - Proper URL parameter loading (like share config links `?c=xxx`)
> - Simulates real production deployment environment
> - Some browser features (like localStorage) may be limited under file:// protocol

## 📁 Project Structure

```
dont-reject-me/
├── index.html      # Main page (confession page)
├── admin.html     # Configuration center (customize content)
└── README.md      # Project documentation
```

## 🔧 How It Works

### Avoidance Logic
```javascript
// Calculate distance when mouse approaches
const distance = Math.hypot(mouseX - btnX, mouseY - btnY);

// Trigger avoidance when distance is less than detection range
if (distance < avoidDistance) {
    moveButtonToRandomPosition();
}
```

### Config Sharing
Configuration is passed via URL parameters using LZString compression + short key optimization:
```
https://domain.com/index.html?c=N4IgjiBc...
```

### Progressive Fun
```javascript
// Increase fun level based on rejection count
const level = Math.min(5, Math.floor((attempts - triggerCount) / 3) + 1);
triggerSpecialEffects(level);
```

## 🤝 Contributing

Welcome to submit Issues and Pull Requests!

1. Fork this repository
2. Create feature branch (`git checkout -b feature/xxx`)
3. Commit changes (`git commit -m 'Add xxx'`)
4. Push branch (`git push origin feature/xxx`)
5. Create Pull Request

## 📄 License

MIT License - Free to use and modify

---

Made with ❤️ for fun confessions
