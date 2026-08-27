# 🎧 Y2K Rewind · NJZ Pixel Archive

[![Live Demo](https://img.shields.io/website?url=https%3A%2F%2Fe-ver1024.github.io%2FNewjeans%2F&label=Live%20Demo&style=for-the-badge&color=e6aebb&labelColor=3e5470)](https://e-ver1024.github.io/Newjeans/)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Newjeans-7a99bc?style=for-the-badge&logo=github)](https://e-ver1024.github.io/Newjeans/)

> 🌐 **在线访问**：<https://e-ver1024.github.io/Newjeans/>

一个可交互的数字怀旧空间，把 NewJeans 的 Y2K 美学、青春叙事与复古像素艺术深度融合，把"听歌"转化为"探索记忆"的体验。

整个网站由单个 `index.html` 文件实现，零依赖、零构建步骤，纯前端即可运行。

---

## ✨ 核心特性

### 启动页 · 随身听
- CRT 扫描线 + 像素光标 + 电视雪花过渡
- 复古按钮音效（方波咔哒 + 带通滤波噪声脉冲，模拟机械接触感）
- PLAY 按钮进入主界面

### 翻盖手机导航
- 右下角的像素翻盖手机，点击屏幕放大 / 缩小
- 放大后顶部显示 NewJeans 风格的真实时钟（粉色发光阴影、闪烁冒号）
- 屏幕上方有飘动的、大小不一的彩色像素音符
- 缩小状态下提供 ▲▼◀▶ 四向方向键用于切换页面

### 复古收音机音乐播放器
- 木纹纹理 + 金属网格 + 皮革提手 + 铆钉 + 频率刻度盘 + 底部铭牌
- 7 种皮肤配色（原木 / 赤红 / 海蓝 / 柠黄 / 暖橙 / 薄荷绿 / 樱花粉），右上角↻按钮一键切换
- 专辑封面像拍立得一样从收音机上方弹出 / 收回，带 0.9s 缓动动画
- 切歌、音量、歌单、歌曲选择一应俱全
- 第一首歌加载过程中屏幕上有实时缓冲进度条

**歌单**
1. Ditto · 90.0 MHz
2. NewJeans · 90.5 MHz
3. Supernatural
4. …（频率递增）

### NJZ Diary 日记
- 6 篇日记，每篇带封面图与日期
- 显示原图，不加任何像素特效

### MV Rewind · 像素飞天小女警游戏
- 玩家操控粉色 Blossom，击杀三种像素怪物
- 收集青 / 粉 / 蓝 / 黄四色糖果，达到 500 分胜利
- 生命值 3 颗心，归零则游戏结束
- 开始 / 重玩 / 胜利按钮统一通过 `▶ START / RETRY / PLAY AGAIN` 触发
- 视图切换时自动暂停 / 恢复

### 照片墙
- 白色相框 + 日期 + 图钉，可随意拖动
- 每张相框倾斜角度随机

### Bunnies Lounge 留言墙
- 弹幕式留言从天花板飘落
- 像素表情支持

### Merch Pixel Shop
- 像素风周边商品陈列

### About 彩蛋页
- 复古 Windows 弹窗堆叠
- 标题"NJZ PIXEL ARCHIVE"
- 弹窗可关闭、可拖动

---

## 🎮 操作说明

| 场景 | 操作 |
| --- | --- |
| 启动页 | 点击 PLAY 或按回车进入 |
| 翻盖手机 | 点击屏幕放大 / 缩小 |
| 缩小状态 | ▲ 跳首项（HOME）／ ▼ 跳末项（ABOUT）／ ◀▶ 循环切换 |
| 飞天小女警 | ← → 移动 · ↑/W/SPACE 飞行 · ↓ 下降 · X 或回车 射击 |
| 飞天小女警 | 回车 / R 键开始或重玩（游戏进行中回车触发射击）|
| 彩蛋 | Konami 代码 ↑↑↓↓←→←→BA 触发隐藏小游戏 |

---

## 🛠 技术栈

- **HTML5 / CSS3 / JavaScript (ES6+)** — 单文件实现
- **Canvas API** — 像素图像绘制（字符串数组 + 调色板）
- **Web Audio API** — 合成 BGM、环境音、交互音效
- **HTML5 Audio** — 播放真实音频文件
- **CSS 动画 + requestAnimationFrame** — 视觉效果与游戏循环
- **localStorage** — 保存用户收集的心情贴纸位置
- **IIFE 模块化** — Diary / MV / Radio / Wall / Lounge / Shop / About 独立封装

### 性能优化
- 首页像素小人由代码实时绘制，无需图片资源
- 移除冗余字体（DotGothic16，减少 12 个 woff2 请求）
- 动画降频（CRT 噪点动画 1.2s → 4s）
- 加载时间从 53s 优化至 2.65s

---

## 📁 项目结构

```
Newjeans/
├── index.html              # 唯一前端文件（所有功能模块 + 代码绘制像素小人）
├── ditto.mp3               # Ditto 音频
├── newjeans.mp3            # NewJeans 音频
├── 封面图片/                # 日记 / 照片墙 / 歌曲封面共用图片
│   ├── 98bab7e3cc90e35e0ac5f0b4cda12929.jpg   # NewJeans / Super Shy 封面
│   ├── f9eab3326b15ba9713d75d82b104d689.png   # Ditto 封面
│   └── ...
└── README.md               # 本说明文档
```

---

## 🚀 本地运行

由于浏览器对 `file://` 协议有安全限制，需启动本地 HTTP 服务器：

```bash
cd c:\Users\18174\Desktop\Newjeans
python -m http.server 8765
```

打开浏览器访问 http://localhost:8765

---

## 🌐 部署到 GitHub Pages

1. 创建仓库 `e-ver1024/Newjeans`
2. 将所有文件推送到 `main` 分支
3. 进入仓库 Settings → Pages
4. Source 选择 **Deploy from a branch**
5. Branch 选择 **main** / **/ (root)**
6. 保存，等待 1-2 分钟
7. 访问 https://e-ver1024.github.io/Newjeans/

> Pages CDN 可能存在缓存，更新后如未刷新可在 URL 加时间戳参数强制刷新。

---

## 📐 工程约定

- 音符几何体采用低面数设计以保证 VR 性能（如适用）
- 按钮点击音效统一通过 `Audio.click()` 调用
- 音符显示与更新受玩家是否站在舞台上控制，使用 `isOnStage()` 作为门控条件

---

## 📜 License

本项目为粉丝向非商业作品，NewJeans 相关素材版权归原作者所有。
