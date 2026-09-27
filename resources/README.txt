# MGCModpack 发布仓库 —— 强制更新资源清单
#
# ★ 这个文件是给 发布.ps1 读的：它决定哪些文件会被写进公开仓库的
#   manifest.json 的 "resources" 数组，客户端每次启动就照那个数组拉。
#
# ── 两类资源，别混 ────────────────────────────────────────────────
#
#   【强制更新】放这里（Release\resources\）
#     每次启动都拉，哈希一致就跳过。适合：
#       文案表、公告、小图标、配置片段、UI 覆盖文件
#     判据：体积小、人人都要、缺了会出错
#
#   【按需下载】**不要**放这里（走 mod\ 和 map\ 目录，见下）
#     玩家在游戏里点了才下。适合：
#       .modpack / .mappack 这类几十 MB 的包
#     判据：体积大、只有部分人要
#     ★ 混进来的后果：每个玩家每次启动都要校验一遍几百 MB 的文件，
#       启动时间直接崩掉。
#
# ── 目录约定（公开仓库）──────────────────────────────────────────
#
#   manifest.json          必须在根目录 —— 客户端地址写死了，动了就拉不到更新
#   README.md              必须在根目录 —— GitHub 首页要显示它
#   config\config.json     运营配置（白名单/版本/关于页文案/面板图…）
#   icon\*.png             图标（about-icon / announcement-icon / panel-placeholder）
#   bundle\*.unity3d       UI 资源包（AssetBundle）
#   resources\<name>       本文件声明的强制更新资源（name 可带子目录）
#   mod\mods.json          .modpack 索引（游戏内「Mod 管理 → 下载」读它）
#   map\maps.json          .mappack 索引（地图页「下载」视图读它）
#
#   mod\<文件>.modpack     实际的包
#   map\<文件>.mappack
#
# ── 怎么用 ──────────────────────────────────────────────────────
#
#   1. 强制更新资源：丢进 UpdateSystem\Release\resources\，跑 发布.ps1
#   2. 包：丢进 UpdateSystem\Release\mod\ 或 map\，跑 发布包.ps1
#      （它会算哈希、生成 mods.json / maps.json 索引、上传）
#
# 这个文件本身只是说明，不被脚本读取（脚本扫的是 resources\ 目录）。
