# GettingOverIt-MGCModpack

《Getting Over It（掘地求升）》手机版的**非官方扩展模组包**，这里是它的**发布仓库**。

这个仓库只做一件事：**当更新服务器**。游戏里的 `MGCLoader` 启动时来这儿拉版本清单、配置和产物，
所以这里只有清单、配置和编译好的文件，**没有源码**。

- 作者 Bilibili：[@aWinHimOP](https://github.com/aWinHimOP)
- QQ 交流群：549361403

## 仓库内容

| 路径 | 说明 |
|---|---|
| `index.json` | 版本清单，客户端启动时拉这个 |
| `versions/` `bundle/` `picture/` | 各版本的 DLL、UI 资源包、图标 |
| `mod/` `map/` | 官方 mod 与地图（客户端直接从这里下载） |
| `config/` `announcements.json` | 运营配置与公告 |
| `netdisk.json` | 服务器不可用时的网盘备用渠道 |
| `server.json` | 地址发布（已停用下载服务器） |

## 引用的开源项目

本项目的一部分来自这些项目，感谢作者：

| 项目 | 许可证 | 用在哪 |
|---|---|---|
| [DearVa/Unity-Runtime-Inspector](https://github.com/DearVa/Unity-Runtime-Inspector) | MIT | `InGameDebugger.dll` |
| [JamesNK/Newtonsoft.Json](https://github.com/JamesNK/Newtonsoft.Json) | MIT | JSON 处理 |
| [MelvinShwuaner/IL2CPP2MONO](https://github.com/MelvinShwuaner/IL2CPP2MONO) | MIT | 把 IL2CPP 转成 Mono 的工具链 |
| [mono/cecil](https://github.com/mono/cecil) | MIT | 程序集读写（Mono.Cecil） |
| [gree/unity-webview](https://github.com/gree/unity-webview) | zlib | 排行榜内嵌浏览器的**做法参考**（见下） |

> **关于排行榜的内嵌浏览器：为什么没有直接用 gree/unity-webview。**
> 它是最常用的免费方案（zlib 许可证），但它需要往游戏 APK 里放 Java 类和 native 库，
> 而本模组包是**热更的 DLL** —— 游戏本体早就装在玩家手机上了，DLL 改不了 APK，
> 所以任何插件（免费的、付费的都一样）都装不进去。
> 好在**不做插件也能做**：Unity 自带的 `AndroidJavaObject` 本来就能调 Java，
> 于是用 JNI 直接叫起系统的 `android.webkit.WebView`，**纯 C# 实现，不要钱、不改 APK**。
> 万一在某些机型上起不来，会**退回系统浏览器**打开，功能不会没有。

## 免责声明

1. **非官方作品。** 本项目由玩家自发制作，与《Getting Over It with Bennett Foddy》的
   开发者 Bennett Foddy、中国区代理 ZPLAY、发行商 Noodlecake Studios 及任何相关公司
   **没有任何隶属、合作或背书关系**。

2. **游戏版权归原作者。** 游戏的程序集与全部资源（美术、音频、代码、商标等）
   版权属于 Bennett Foddy 及 ZPLAY。本项目**不包含游戏本体**，也不主张对游戏任何部分的权利。

3. **必须拥有正版。** 本项目只对已合法购买并安装的游戏生效，不得用于获取或运行盗版。

4. **使用风险自负。** 修改运行时行为属于非官方修改，可能导致**崩溃、存档损坏、进度丢失**
   或与其他软件冲突。本项目按「现状」提供，不提供任何担保，作者不承担由此产生的损失。

5. **在线请求。** 客户端会访问本仓库以获取清单、配置与图标，这些请求不含个人信息。

**不同意以上任何一条请不要使用。**

---

完整许可证见 [LICENSE](LICENSE)（MIT，仅适用于本仓库的代码）。