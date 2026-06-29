# Yaozhil MPV 整合包

这是一个面向 Windows 用户的 mpv 自制 UI 整合包，最初基于 [dyphire/mpv-config](https://github.com/dyphire/mpv-config) 的配置结构继续整理，现在重点加入了更适合中文追剧、弹幕和鼠标操作的 uosc 体验。

本仓库用于展示公开版说明、特色截图和通用配置。完整便携整合包请通过 Release 或网盘附件分发，不建议把包含 `mpv.exe` 的整包直接提交进 Git 历史。

## 界面预览

![主界面标注](docs/images/ui-annotated.png)

更多截图：

- [底栏细节](docs/images/player-bar-annotated.png)
- [网盘登录面板](docs/images/alist-login-annotated.png)
- [空闲网盘入口](docs/images/webdav-entry-annotated.png)

## 这版独特功能

相对原始上游整合包，这一版的核心变化集中在 UI 操作、中文内容和追剧工作流：

- **uosc 底栏重排**：打开文件、弹幕、字幕、倍速、片头片尾、播放列表和更多菜单集中在底栏，鼠标操作更直接。
- **中文弹幕工作流**：保留弹幕搜索、匹配、加载和提示，并把弹幕入口独立放到底栏。
- **片头片尾标记与自动跳过**：接入片头片尾按钮，支持联网片段、本地手动修正和自动跳过。
- **中文化 stats**：解码、HDR、帧耗时、音频和渲染状态用中文显示，更适合普通用户排查播放状态。
- **AList/OpenList 网盘入口**：空闲底栏新增网盘按钮，并提供内置登录/保存面板。
- **公开版清理**：发布目录不包含本机播放历史、缓存、日志、watch_later、个人 token 和固定设备路径。

详细说明见 [独特功能说明](docs/unique-features.md)。

## 下载与安装

1. 从 Release 或网盘下载完整整合包。
2. 解压后运行同级目录中的 `mpv.exe`。
3. 如果只使用配置目录，可把 `portable_config` 放到自己的 `mpv.exe` 同级目录。
4. 首次替换前建议备份原有 mpv 配置。

部分功能需要系统可运行 `curl`、`ffmpeg`、`yt-dlp` 或 `alass`。缺少这些工具时，基础播放不受影响，相关增强菜单会不可用或降级。

## 发布包建议

当前桌面整合包为：

```text
C:\Users\杳知\Desktop\mpv（杳知整合包）6.29.zip
```

这个 ZIP 适合作为 Release 附件或网盘下载文件；仓库本体建议只放配置、说明和展示图。发布前请优先使用 ZIP 内的 `dist/mpv-config-release/` 作为公开清洁版依据。

发布检查见 [发布前检查](docs/release-check.md)。

## 来源与致谢

- [dyphire/mpv-config](https://github.com/dyphire/mpv-config)
- [yosh-wang/mpv-stats.lua-zh-chinese-translation-](https://github.com/yosh-wang/mpv-stats.lua-zh-chinese-translation-)
- mpv 社区脚本、shader 与相关开源项目

各脚本、shader 与第三方组件的版权和许可归原作者所有。若上游项目自带 README / LICENSE，发布整合包时应尽量保留原始说明。

## 免责声明

本配置主要面向 Windows mpv 用户。不同 mpv 构建、显卡驱动、系统版本和脚本依赖环境可能导致体验不同。遇到播放异常时，建议先尝试关闭 shader、改用 `hwdec=no`、关闭部分第三方脚本或升级 mpv。
