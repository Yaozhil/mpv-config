# Yaozhil mpv config

面向 Windows mpv 的中文化 `portable_config` 配置包，基于 `dyphire/mpv-config` 的配置结构整理，并加入个人维护的 uosc 布局、快捷键菜单、弹幕、片头片尾标记与中文统计信息体验。

本发布版已经做通用化处理：不固定显卡、不固定具体音频设备、不写死本机 mpv 路径，不包含播放历史、缓存、截图、watch_later 与个人 API secret。

> 上游参考：`dyphire/mpv-config` 是 Windows 下 mpv 配置项目；`yosh-wang/mpv-stats.lua-zh-chinese-translation-` 提供中文版 stats.lua 思路与同步说明。

## UI 预览

![UI 预览](docs/images/ui-preview.jpg)

## 当前仓库状态

当前仓库已先上传公开说明、通用核心配置、快捷键预设、脚本选项示例和 UI 预览。完整本地整理包中还包含更多第三方脚本、shader 与资源文件；继续同步时请保留原作者 README / LICENSE，避免提交个人运行数据、字体二进制和私密 token。

## 安装

1. 下载整合包（zip)解压即可使用
2.内含 杳知配置助手（MPV）.exe
3.打开配置助手按需配置即可（会自动获取）

## 主要特色

- uosc 中文界面与菜单体验优化
- 常用 UI 操作、播放控制、文件管理、字幕、音轨和播放列表快捷键整理
- 集成弹幕相关配置
- 新增片头片尾跳过
- 新增纯本地化 自定义 片头片尾设置工具（✂图标）
- 新增Alist登陆弹窗+☁图标（Alist相关全适配）
- 新增：本地 iso 视频格式播放
- 重写：文件浏览器鼠标操作（支持鼠标悬停高亮提示）

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
├─ custom-updates.md     # 本维护版特色说明
└─ images/ui-preview.jpg # UI 预览图
```

## 快捷键提示

不同用户习惯不同，快捷键可以直接在 `portable_config/input.conf` 内修改。

常用方向：

- 文件与目录打开
- 播放 / 暂停 / 快进 / 后退
- 字幕延迟与字幕轨切换
- 音频轨切换
- uosc 菜单与播放列表
- 置顶 / 迷你窗口 / 截图等 UI 操作

详细说明见：[`docs/custom-updates.md`](docs/custom-updates.md)

## 许可与来源说明

本仓库整理自个人使用配置，并参考以下项目结构或思路：

- `dyphire/mpv-config`
- `yosh-wang/mpv-stats.lua-zh-chinese-translation-`
- mpv 社区脚本与相关开源项目

各脚本、shader 与第三方组件的版权和许可归原作者所有。若上游项目自带 LICENSE / README，本仓库会尽量保留原始说明。

## 免责声明

本配置主要面向 Windows mpv 用户。不同 mpv 构建、显卡驱动、系统版本和脚本依赖环境可能导致体验不同。遇到播放异常时，建议先尝试：

