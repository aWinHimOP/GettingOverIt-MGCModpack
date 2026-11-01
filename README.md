<div align="center">

<img src="picture/about-icon.png" width="120" alt="MGC Modpack">

# MGC Modpack

**《Getting Over It（掘地求升）》手机版的非官方扩展模组包**

热更新 · Mod 系统 · 地图包 · 内置资源下载

[**🌐 官网 / 下载页**](https://awinhimop.github.io/GettingOverIt-MGCModpack/) · Bilibili **@aWinHimOP** · QQ 群 **549361403**

</div>

---

## 这是什么

给《Getting Over It》安卓版**加一层可热更新的扩展**。

游戏本体一个字节都不改 —— 启动时由 `MGCLoader` 把逻辑挂到游戏进程上，
所以修 bug、加功能都**不用重新分发安装包**，玩家下次启动自动就是新版。

这个仓库只做一件事：**当更新服务器 + 项目主页**。
客户端启动时来这里拉版本清单、配置和更新文件；官网也放在这里。

> ### ⚠ 本仓库不提供安装包
>
> **GitHub 仓库和 GitHub Pages 上都不放 APK，也不放游戏本体。**
> 下载请走官网的[下载页](https://awinhimop.github.io/GettingOverIt-MGCModpack/download.html)（网盘渠道）。
> 这里只存放版本清单、配置和热更新用的文件，**不构成对游戏或成品的再分发**。

## 功能

| | 功能 | 说明 |
|---|---|---|
| ⚡ | **热更新** | 启动比对版本清单，只下变动的 DLL 和资源包 |
| 🧩 | **Mod 系统** | 存档、计时器、光标美化、自定义背景、碰撞箱显示、快速出罐、TNT、触摸可视化……游戏内逐项开关 |
| 🗺️ | **地图包** | 官方地图 + 社区地图，资源页点一下就能下 |
| 📦 | **内置资源页** | Mod 和地图不用去别处找，游戏里就是下载入口，还带网盘备用渠道 |
| 💬 | **公告与远程 UI** | 公告、通知、问题反馈都在游戏内 |
| 🏆 | **成绩统计** | 分段计时、最佳成绩、重开次数、通关次数，存本地 |

## 安装

1. 从 [下载页](https://awinhimop.github.io/GettingOverIt-MGCModpack/) 拿安装包
2. 首次启动自动同步最新版本（需要联网）
3. 进游戏，左上角暂停键 → 左侧菜单就是各个页面
4. 「社区/资源」页下载 Mod / 地图，在「Mod(模组)」「Map(地图)」里启用

> 只支持 **安卓**，游戏版本 **1.9.2**。

## 仓库内容

| 路径 | 说明 |
|---|---|
| `index.html` | 官网首页（GitHub Pages 根页） |
| `download.html` | 下载页：本体 / 地图包 / 模组包（读 `netdisk.json`） |
| `guide.html` `faq.html` `shots.html` `disclaimer.html` | 教程 / 常见问题 / 实机截图 / 声明 |
| `site.css` | 全站样式 |
| `index.json` | 版本清单，客户端启动时拉这个 |
| `releases/` `bundle/` `picture/` | 各版本的 DLL、UI 资源包、图标 |
| `mod/` `map/` | 官方 mod 与地图（客户端直接从这里下载） |
| `community/` | 社区投稿的 mod / 地图清单 |
| `config/` `announcements.json` | 运营配置与公告 |
| `netdisk.json` | 网盘备用渠道（**官网的下载列表也读这个**） |
| `channels.json` | 正式 / 测试双频道配置 |
| `server.json` | 更新服务器地址 |

## 用到的开源项目

下面按**实际使用情况**逐项列出，包括用在哪、有没有随成品分发 —— 方便核对，避免误标。

### 随成品分发

| 项目 | 许可证 | 用在哪 | 备注 |
|---|---|---|---|
| [DearVa/Unity-Runtime-Inspector](https://github.com/DearVa/Unity-Runtime-Inspector) | MIT | 游戏内调试面板：`MGC/Managers/DebugPanelManager.cs` 调用其 `InGameDebugger` API | 以 `InGameDebugger.dll` 形式打进 APK 的冻结层 |

### 仅构建 / 开发工具（不随成品分发）

| 项目 | 许可证 | 用在哪 |
|---|---|---|
| [jbevain/cecil](https://github.com/jbevain/cecil)（Mono.Cecil） | MIT | `Tools/ILVaultGui`、`Tools/VMObfuscator` 的程序集读写 |
| [icsharpcode/ILSpy](https://github.com/icsharpcode/ILSpy)（ICSharpCode.Decompiler） | MIT | 反编译辅助工具 |
| [MelvinShwuaner/IL2CPP2MONO](https://github.com/MelvinShwuaner/IL2CPP2MONO) | MIT | 把游戏从 IL2CPP 转成 Mono 的工具链 |

以上许可证文本以各项目仓库为准。

## 免责声明

1. **非官方作品。** 本项目由玩家自发制作，与《Getting Over It with Bennett Foddy》的
   开发者 Bennett Foddy、中国区代理 ZPLAY、发行商 Noodlecake Studios 及任何相关公司
   **没有任何隶属、合作或背书关系**。

2. **游戏版权归原作者。** 游戏的程序集与全部资源（美术、音频、代码、商标等）
   版权属于 Bennett Foddy 及 ZPLAY。本项目**不包含游戏本体**，也不主张对游戏任何部分的权利。

3. **必须拥有正版。** 本项目只对已合法购买并安装的游戏生效，不得用于获取或运行盗版。

4. **本仓库不托管安装包。** GitHub 仓库与 GitHub Pages 上**不放 APK、不放游戏本体、不放成品安装包**，
   只存放版本清单、配置与热更新文件。所有安装包仅通过网盘等第三方渠道分发，与 GitHub 无关。

5. **禁止商业用途。** 不得售卖、付费分发、捆绑推广或以任何形式从中获利。

6. **使用风险自负。** 修改运行时行为属于非官方修改，可能导致**崩溃、存档损坏、进度丢失**
   或与其他软件冲突。本项目按「现状」提供，不提供任何担保，作者不承担由此产生的损失。

7. **不收集个人信息。** 客户端会访问本仓库以获取清单、配置与图标，这些请求不含个人信息。

8. **素材来源。** 项目内部分素材来自网络，版权归原作者所有；如有侵权请联系删除。

**不同意以上任何一条请不要使用。**

---

完整许可证见 [LICENSE](LICENSE)（MIT，仅适用于本仓库的代码）。