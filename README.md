# Yaozhil MPV 整合包

面向 Windows mpv 的中文化自制 UI 整合包，最初基于 [dyphire/mpv-config](https://github.com/dyphire/mpv-config) 的配置结构继续整理，并加入个人维护的 uosc 布局、快捷键菜单、弹幕、片头片尾标记、AList/OpenList 网盘入口和中文统计信息体验。

本发布版已经做通用化处理：不固定显卡、不固定具体音频设备、不写死本机 mpv 路径，不包含播放历史、缓存、截图、watch_later 与个人 API secret。

> 上游参考：`dyphire/mpv-config` 是 Windows 下 mpv 配置项目；`yosh-wang/mpv-stats.lua-zh-chinese-translation-` 提供中文版 stats.lua 思路与同步说明。

## UI 预览

![主界面标注](docs/images/ui-annotated.png)

更多截图：

- [底栏细节](docs/images/player-bar-annotated.png)
- [网盘登录面板](docs/images/alist-login-annotated.png)
- [空闲网盘入口](docs/images/webdav-entry-annotated.png)

## 安装

1. 下载整合包 ZIP，解压即可使用。
2. 内含 `杳知配置助手（MPV）.exe`。
3. 打开配置助手，按需配置即可（会自动获取）。
4. 如果只想使用配置目录，可把 `portable_config` 放到自己的 `mpv.exe` 同级目录。

## 主要特色

- uosc 中文界面与菜单体验优化。
- 常用 UI 操作、播放控制、文件管理、字幕、音轨和播放列表快捷键整理。
- 集成弹幕相关配置。
- 新增片头片尾跳过。
- 新增纯本地化自定义片头片尾设置工具（剪刀图标）。
- 新增 AList/OpenList 登录弹窗和网盘图标（AList 相关适配）。
- 新增本地 ISO 视频格式播放。
- 重写文件浏览器鼠标操作，支持鼠标悬停高亮提示。
- 中文化 stats，方便查看解码、HDR、帧耗时和音频状态。

详细说明见 [独特功能说明](docs/unique-features.md)。

## 目录说明

```text
portable_config/
├─ mpv.conf              # mpv 主配置，通用硬件默认值
├─ input.conf            # 快捷键与菜单预设
├─ scripts/README.md     # 脚本同步说明
├─ script-opts/          # 脚本选项示例
├─ shaders/README.md     # shader 同步说明
└─ fonts/README.md       # 字体说明，不附带字体文件
docs/
├─ unique-features.md    # 本维护版特色说明
├─ release-check.md      # 发布前检查
└─ images/               # UI 展示图
```

## 发布说明

完整便携整合包建议通过 GitHub Release 或网盘分发，不建议把包含 `mpv.exe` 的完整 ZIP 直接提交进 Git 历史。

当前桌面整合包：

```text
C:\Users\杳知\Desktop\mpv（杳知整合包）6.29.zip
```

发布前检查见 [发布前检查](docs/release-check.md)。

## 许可与来源说明

本仓库整理自个人使用配置，并参考以下项目结构或思路：

- [dyphire/mpv-config](https://github.com/dyphire/mpv-config)
- [yosh-wang/mpv-stats.lua-zh-chinese-translation-](https://github.com/yosh-wang/mpv-stats.lua-zh-chinese-translation-)
- mpv 社区脚本与相关开源项目

各脚本、shader 与第三方组件的版权和许可归原作者所有。若上游项目自带 LICENSE / README，本仓库会尽量保留原始说明。

## 免责声明

本配置主要面向 Windows mpv 用户。不同 mpv 构建、显卡驱动、系统版本和脚本依赖环境可能导致体验不同。遇到播放异常时，建议先尝试关闭 shader、改用 `hwdec=no`、关闭部分第三方脚本或升级 mpv。
