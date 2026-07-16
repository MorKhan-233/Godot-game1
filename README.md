
# Fox vs Slime 🦊👾

> **Godot 4.6 2D 像素风横版射击小游戏**

![游戏截图](images/screenshot.png)
*（在此处放入游戏运行截图）*

## 项目简介

一款使用 Godot 4.6 引擎开发的 2D 像素风格射击小游戏。玩家操控狐狸角色，在森林场景中抵御不断来袭的史莱姆敌人，通过射击获取分数，体验随时间递增的挑战难度。

## 玩法说明

| 操作 | 按键 |
|------|------|
| 移动 | W / A / S / D |
| 射击 | 空格键 |

- 史莱姆从画面右侧生成并向左移动
- 在史莱姆碰到你之前将其击倒，每次击杀 +1 分
- 游戏速度会随时间逐渐加快，难度递增
- 被史莱姆碰到则游戏结束，3 秒后自动重开

## 项目结构

```
myfirstgame-2d/
├── Script/          # GDScript 游戏逻辑
│   ├── player.gd        — 角色移动、射击、游戏结束
│   ├── enemy.gd         — 史莱姆碰撞、受击、死亡
│   ├── bullet.gd        — 子弹飞行与自销毁
│   └── GameManager.gd   — 分数、生成、动态难度
├── Scenes/          # 场景文件 (.tscn)
├── AssetBundle/     # 原始资源
│   ├── Sprites/         — 像素贴图（狐狸、史莱姆、子弹、背景）
│   ├── Audio/           — 音效与 BGM
│   └── Uranus_Pixel_11Px.ttf — 像素字体
├── Builds/          # 导出的可执行文件（已 gitignore）
├── export_presets.cfg    — 导出配置
└── project.godot         — 引擎项目配置
```

## 技术要点

- **CharacterBody2D + Area2D** 实现角色与子弹/敌人的碰撞检测体系
- **AnimatedSprite2D** 多状态动画切换（idle / run / death / game_over）
- **动态难度机制**：生成间隔随游戏时长递减，自适应提速
- **Group 标签系统**：通过 `is_in_group("bullet")` 区分碰撞体类型
- **多通道音频管理**：跑步、射击、死亡、BGM 独立播放控制
- **自适应窗口拉伸**：启用 `canvas_items` 模式适配不同分辨率

![游戏演示](images/gameplay.gif)
*（在此处放入游戏演示 GIF）*

## 运行方式

1. 用 [Godot 4.6](https://godotengine.org/download/) 打开项目根目录
2. 点击编辑器顶部 ▶ 运行按钮
3. 或直接运行 `Builds/Windows/Fox vs slime.exe`

## 构建导出

项目内置 Windows 导出预设，可在 Godot 编辑器 → `项目` → `导出` 中选择对应平台一键打包。

## 资源来源

- 像素美术与音效素材来自开源游戏资源网站
- 像素字体：Uranus Pixel 11px

---

*个人作品 · 使用 Godot Engine 4.6 开发*
