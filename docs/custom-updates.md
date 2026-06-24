# 自定义更新说明

此文件记录相对上游配置更偏个人维护方向的改动，方便后续同步 `dyphire/mpv-config` 时保留本包特色。

## UI

- 主 UI 使用 uosc，内置 OSC 默认关闭。
- 底栏采用常驻/最小化进度条思路，按钮集中在底部，适合鼠标操作。
- 底栏加入最近播放、弹幕、片头片尾、播放速度、统计信息、更多菜单等入口。
- 空闲状态显示打开文件、最近播放和按钮提示开关，视频/音频状态显示播放控制、轨道、章节和列表入口。
- 按钮提示可通过底栏开关持久化切换。

## 快捷键与菜单

- `input.conf` 同时维护快捷键和 uosc 右键菜单结构。
- 常用菜单入口：
  - `F7` 播放列表，`F8` 章节，`F10` 音轨，`F11` 字幕。
  - `` ` `` 历史菜单，`N` 书签菜单。
  - `i` 临时统计，`I` 常驻统计。
  - `Alt+Y` 循环音频通道输出。
  - `Alt+N` 手动标记片头片尾，`Alt+Q` 切换章节跳过模式。
- 字幕工作流包含下载、同步、导出、AI 生成和位置/延迟/字号调整。
- 画面工作流包含旋转、缩放、平移、HDR/ICC/色域切换、去色带和着色器菜单。

## 片头片尾

- `skip-segments.lua` 支持 Anime Skip、TheIntroDB、TMDb 标题解析、本地缓存和手动模板。
- 自动跳过开关和手动标记按钮已接入 uosc 底栏。
- 网站片段可被本地手动修正覆盖，移除本地修正后可恢复网站结果。
- 发布版清空 TMDb API key，需要用户自行填写后才能使用依赖 TMDb 的增强查询。

## 弹幕

- uosc 弹幕菜单用于站点搜索、匹配和加载。
- 弹幕历史保存到 `~~/files/danmaku-history.json`，发布仓库不附带个人历史文件。

## 中文统计信息

- 保留中文化 stats 体验，便于普通用户查看解码、渲染、音频、HDR、缓存和性能信息。
- README 已标注 `yosh-wang/mpv-stats.lua-zh-chinese-translation-` 作为中文统计脚本参考。

## 发布版清理策略

- 不发布本机播放器二进制、LuaJIT 可执行文件、运行日志、历史记录、截图、shader cache 和 watch_later。
- 不发布本机绝对路径、音频设备 GUID、GPU 型号绑定和第三方服务 secret。
- 不发布字体二进制文件；保留 `portable_config/fonts/README.md` 说明补充方式。
- 保留 `cache/.gitkeep` 与 `files/.gitkeep`，让运行期目录结构清晰存在。

## 通用化处理记录

- `gpu-api=d3d11` 改为默认注释，避免强制所有用户使用同一图形 API。
- `hwdec=d3d11va` 改为 `hwdec=auto-safe`，避免绑定 Windows d3d11va。
- `d3d11-adapter` / `vulkan-device` 清空示例，防止误绑定某台电脑的 GPU。
- 文件浏览器中固定 Firefox 安装路径改成系统默认打开方式。
- ASSRT、OpenSubtitles 等可能涉及个人或项目凭据的默认 token 已清空。
