# 🐈‍⬛ KuroCat Neo

> 一只透明置顶的桌面打字猫咪。基于 [qianyiai/kurocat](https://github.com/qianyiai/kurocat) 二开增强，独立版本线（`0.1.x`）。
>
> 轻量单文件 · 零外部运行时依赖 · **Tauri v2（Rust 全局原生钩子 + 内置 MCP 引擎 + HTML5 Canvas 2D）**
> 跨平台：**Windows 10/11 · macOS 10.15+（Apple Silicon & Intel）· Linux（Ubuntu / 银河麒麟 / UOS，x86_64 & ARM64）**

---

## 🌟 本仓库增强功能（相对上游）

| 功能 | 说明 |
|------|------|
| **🐾 择机而动（自动隐身）** | 无键鼠输入时猫咪自动淡出隐身，任意键盘 / 鼠标 / 滚轮输入瞬间弹性唤醒。隐身延时 **1 / 3 / 5 / 10 秒** 可调，隐身期间完全鼠标穿透不挡操作，托盘一键开关 |
| **🎾 滚轮撸猫跑步** | 滚轮滚动触发猫咪原地走路 / 跑步动画，滚动越快跑越欢 |
| **💥 尾巴拍地板 + 黑白漫画冲击星** | 摸头触发呼噜声的同时，尾巴像真猫被打扰一样 rhythmic 甩尾拍地板——尾巴尖甩下贴地再弹回，接触瞬间炸出**黑白漫画风冲击星**；星星大小严格按尾巴实际粗细自适应（半径 = 尾巴线宽 × 1.5），摸得越久拍得越快（0.82s → 0.44s/拍），全毛色通用 |
| **🖱️ 全新拖拽体验** | 拖拽改由 Windows 全局低级鼠标钩子直接驱动（按下命中猫身即接管），Win10 / Win11 下稳定跟手，告别间歇性拖不动 |
| **✅ 独立检查更新** | 应用内检查更新 / 一键升级指向**本仓库** Releases，不再依赖原作者发布渠道 |

---

## ✨ 全功能总览

### 🐱 外观与皮肤
- **7 款内置皮肤**，右键 / 托盘 0.1 秒无缝切换：
  🐈‍⬛ 经典小黑猫 · 🐱 暖奶茶布偶猫 · 🍊 大橘猫（虎斑 `M` 额纹 + 环纹尾） · 🌸 三花猫 · 🐄 奶牛猫（燕尾服 + 白手套） · 🤎 暹罗猫（挖煤重点色） · 🐳 大肥鱼（鲸鱼娘，三肢同步键鼠 + 鲸尾拍打水花 + 手速腮红）
- **MCP 无限自定义皮肤**：把自家猫照片发给 AI，一句话捏出独一无二的桌宠（毛色 / 花纹 / 瞳色 / 白手套 / 胎记斑块），0.4 秒热更新上屏，无需重启
- **20%–150% 无级缩放**，托盘快捷档位 25% / 50% / 75% / 100% / 125% / 150%

### ⌨️ 键盘与输入反馈
- **65% 紧凑 / 108 键全尺寸**双键盘布局（完整 F 区、编辑区、数字小键盘、2U 竖长 `+`、独立 `Num↵`），一键切换并自动调整窗口宽度
- **双视角**：「面向猫咪（180° 真实视角）」/「面向观众（正向易读）」，同步重投影 3D 梯形透视
- **错落弹跳 3D 键帽气泡**：打字时键盘上方实时弹出立体键帽（最多 6 个），可一键隐藏
- **鼠标左 / 右键独立识别高亮** + 3D 按下阴影 + 迷你 `LMB`/`RMB` 气泡，中键 / 滚轮独立区分，支持双键同按
- 打字时头部与上身随敲击节奏左右摇摆歪头，未敲键一侧自动蜷爪收胸

### 🖱️ 互动与动画
- **摸头呼噜**：鼠标移到猫头上变黑白描边小手光标，抚摸触发眯眼表情 + Web Audio 实时合成呼噜声（可开关）
- **尾巴拍地板 + 黑白漫画冲击星**（本仓库新增，见上表）
- **滚轮跑步**（本仓库新增）
- 眨眼、耳朵微抖、日出随机小动作等环境动画

### 🙈 隐私与安全
- **输密码自动闭眼 / 捂眼防偷窥**：Windows（UI Automation + `ES_PASSWORD`）与 macOS（`IsSecureEventInputEnabled` + `AXSecureTextField`）自动感知密码框，Rust 底层拦截真实按键不外传；大肥鱼双手捂眼 + 键盘防窥遮罩
- **智能鼠标穿透**：透明区域自动穿透不挡操作；**「锁定鼠标穿透」**让猫变纯装饰（点它完全穿透），**按住 `Alt` 临时恢复可交互**
- **游戏反作弊护航**：一键「暂停监听并隐藏」，强内核反作弊网游（无畏契约 / 三角洲等）安心玩
- **以管理员身份重启**：游戏管理员权限运行时托盘一键无缝提权捕获键鼠

### 🪟 窗口与系统集成
- **始终置顶** + 无边框 / 全屏优化（FSO）下持续 Z 序置顶守护，绝不抢焦点
- **择机而动自动隐身**（本仓库新增，见上表）
- 托盘菜单：显示/隐藏、重置位置到右下角、创建桌面快捷方式、开机自启、退出
- **App 内检查更新 & 一键升级**：静默检测 → 弹提醒条 → 下载 → SHA-256 校验 → 静默安装重启，指向本仓库 Releases
- **macOS 专属**：键盘监听权限诊断、一键打开「输入监控 / 辅助功能」隐私设置、重新连接键盘监听（兼容 Karabiner-Elements）
- **Windows 7 血统**：上游支持 Win7 SP1（`UpdateLayeredWindow` 256 级逐像素透明），本仓库继承 Win7 分支渲染代码

### 🤖 原生内置 MCP 服务端
- **双模式**：Stdio（`--mcp` 参数，全客户端通用）+ 本机 Streamable HTTP（`http://127.0.0.1:27420/mcp`）
- 零依赖：不需要 Node.js / Python，单文件自带
- 托盘 / 右键一键**复制 MCP 配置**

| 工具名 | 功能 |
| --- | --- |
| `list_cats` | 查看所有内置与自定义猫咪及当前激活的猫 |
| `get_cat_schema` | 获取花色参数规范、6 种花纹、斑点坐标与品种模板 |
| `upsert_cat` | 新增 / 修改自定义猫咪，实时热更新上屏 |
| `switch_cat` | 按 ID 秒切当前猫咪 |
| `delete_cat` | 删除自定义猫咪（或重置内置外观） |
| `get_settings` | 读取缩放 / 气泡 / 呼噜声 / 置顶 / 穿透锁定 / 键盘布局 / 择机而动等全部设置 |
| `update_settings` | 实时修改上述全部设置（含 `keyboardLayout 65\|108`、隐身开关与延时） |

---

## 📥 下载安装

前往 [**Releases**](https://github.com/mengxiangrui1211/kurocat-neo/releases) 下载最新版（`v0.1.9`）：

| 平台 | 安装包 |
|------|--------|
| 🪟 Windows 10/11 x64 | `KuroCat-0.1.9-x64-setup.exe`（约 2 MB，NSIS 安装版，自动创建桌面图标 / 开始菜单 / 卸载入口） |
| 🍎 macOS 10.15+ | `KuroCat-v0.1.9-macos-universal.dmg`（Apple Silicon & Intel 通用）或 `.app.tar.gz` |
| 🐧 Linux x86_64 / ARM64 | `.deb` 或 `.AppImage`（Ubuntu / 银河麒麟 / UOS，X11 XRecord 免 root 捕获，Wayland 自动 evdev 回退） |

**提示**：
- Windows：Edge/Chrome 对未签名 exe 的「保留」操作照常处理即可；精简版系统缺 `WebView2` 时装微软官方引导程序
- macOS：首次打开执行 `xattr -cr /Applications/KuroCat.app`，并在「系统设置 → 隐私与安全性」给 `KuroCat` 勾选**辅助功能 + 输入监控**
- Windows 配置目录：`%APPDATA%\kuro-cat-pet\`（`settings.json` / `cats.json`，可手动编辑，实时热重载）

---

## 🤖 MCP 接入指南

1. 运行 `KuroCat`，右键 → 勾选 **「开启 MCP 扩展服务」** → **「复制 MCP 配置」**
2. 粘贴到 Claude Desktop / Cursor / Cline 等客户端：

```json
{
  "mcpServers": {
    "kurocat": {
      "command": "D:\\Program Files\\KuroCat\\KuroCat.exe",
      "args": ["--mcp"]
    }
  }
}
```

或 HTTP 直连（桌宠运行时）：

```json
{ "mcpServers": { "kurocat": { "url": "http://127.0.0.1:27420/mcp" } } }
```

3. 试试这样跟 AI 说：
   - *「用 KuroCat MCP 按我家猫的照片捏一只专属桌宠并切过去」*
   - *「把桌宠放大到 125%，关闭按键气泡，开启择机而动 5 秒隐身」*
   - *「切到 108 键全尺寸键盘，键盘高亮换成橘色」*

---

## 🛠️ 本地源码构建

前置环境：Node.js 18+、Rust 工具链（`cargo`）。

```bash
git clone https://github.com/mengxiangrui1211/kurocat-neo.git
cd kurocat-neo
npm install
npm run tauri:dev      # 本地热更新调试
npm run tauri:build    # 编译 Release 安装包
```

推送 tag（`v*`）自动触发 GitHub Actions 三平台构建并生成 Release 草稿。

---

## 📄 开源协议与致谢

- 本项目基于 [MIT License](LICENSE) 开源
- 上游项目：[qianyiai/kurocat](https://github.com/qianyiai/kurocat) —— 感谢原作者的优秀作品，本仓库在其基础上独立增强开发
- 内置皮肤 **🐳 大肥鱼（鲸鱼娘）** 运行时素材基于 MIT 开源项目 [PC2005-cloud/dsh-pet](https://github.com/PC2005-cloud/dsh-pet) 制作，许可声明见 `src/assets/dafeiyu/LICENSE-MIT.txt`
