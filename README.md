# Yaozhil mpv config

面向 Windows mpv 的中文化 `portable_config` 配置包，基于 `dyphire/mpv-config` 的配置结构整理，并加入个人维护的 uosc 布局、快捷键菜单、弹幕、片头片尾标记与中文统计信息体验。

本发布版已经做通用化处理：不固定显卡、不固定具体音频设备、不写死本机 mpv 路径，不包含播放历史、缓存、截图、watch_later 与个人 API secret。

> 上游参考：`dyphire/mpv-config` 是 Windows 下 mpv 配置项目；`yosh-wang/mpv-stats.lua-zh-chinese-translation-` 提供中文版 stats.lua 思路与同步说明。

## UI 预览

![UI 预览](docs/images/ui-preview.png)

## 安装

1. 下载或克隆本仓库。
2. 将 `portable_config` 文件夹放到 `mpv.exe` 同级目录。
3. 也可以把 `portable_config` 内的文件复制到 `%APPDATA%/mpv/`，作为全局 mpv 配置使用。
4. 首次使用前建议备份原有 mpv 配置。

建议使用较新的 mpv Windows 构建，例如 shinchiro 或 zhongfly 的 mpv 构建。部分功能需要系统 PATH 中可找到 `curl`、`ffmpeg`、`yt-dlp` 或 `alass`；没有这些工具时，相关菜单项会不可用，但基础播放不受影响。

## 发布版通用化

- **显卡**：不固定 `d3d11-adapter` / `vulkan-device`，由系统自动选择 GPU。
- **图形 API**：默认不强制 `gpu-api=d3d11`；需要 Windows d3d11 的用户可自行取消注释。
- **硬解**：`hwdec=auto-safe`，让 mpv 选择安全硬件解码；兼容异常时可改为 `no`。
- **音频**：不固定 `audio-device`，`audio-channels=auto-safe`，不强制某个品牌设备或双声道。
- **路径**：不写入本机用户目录绝对路径；截图、缓存、弹幕历史等运行数据统一放在 `~~/` 或 mpv 默认配置目录。
- **隐私**：已移除播放历史、观看记录、缓存、token、trakt secret 等运行态信息。

## 主要特色

- uosc 中文界面与菜单体验优化。
- 常用 UI 操作、播放控制、文件管理、字幕、音轨和播放列表快捷键整理。
- 集成弹幕相关配置，适合中文用户使用。
- 保留片头片尾跳过、章节识别、播放历史菜单等增强功能。
- 中文化 stats 体验，方便查看播放与渲染信息。
- 提供常见 shader、脚本和脚本配置，适合直接作为便携版 mpv 配置使用。

## 目录说明

```text
portable_config/
├─ mpv.conf              # mpv 主配置
├─ input.conf            # 快捷键配置
├─ scripts/              # Lua 脚本
├─ script-opts/          # 脚本选项
├─ shaders/              # shader 文件
├─ script-modules/       # 脚本依赖模块
├─ fonts/                # 字体目录说明，不附带字体文件
└─ icc/                  # 色彩配置文件
docs/
├─ custom-updates.md     # 本维护版特色说明
└─ images/ui-preview.png # UI 预览图
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

## 与个人版的区别

这个仓库是公开发布的通用版，不包含以下内容：

- 你的电脑专属路径
- 你的固定显卡选择
- 你的固定音频设备
- 你的播放历史
- 你的截图、缓存、watch_later
- 你的 API key / token / secret
- 私有字体文件

如果你想恢复自己的电脑专属优化，可以在本仓库基础上另建本地私有覆盖配置。

## 许可与来源说明

本仓库整理自个人使用配置，并参考以下项目结构或思路：

- `dyphire/mpv-config`
- `yosh-wang/mpv-stats.lua-zh-chinese-translation-`
- mpv 社区脚本与相关开源项目

各脚本、shader 与第三方组件的版权和许可归原作者所有。若上游项目自带 LICENSE / README，本仓库会尽量保留原始说明。

## 免责声明

本配置主要面向 Windows mpv 用户。不同 mpv 构建、显卡驱动、系统版本和脚本依赖环境可能导致体验不同。遇到播放异常时，建议先尝试：

1. 临时关闭 shader。
2. 将 `hwdec=auto-safe` 改为 `hwdec=no`。
3. 关闭部分第三方脚本。
4. 使用最新版 mpv。
