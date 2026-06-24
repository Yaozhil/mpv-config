# portable_config

这是公开仓库的通用版配置目录。

## 使用方式

将整个 `portable_config` 文件夹放到 `mpv.exe` 同级目录即可作为便携配置使用；也可以将其中内容复制到 `%APPDATA%/mpv/`。

## 通用化原则

- 不绑定某台电脑的绝对路径。
- 不绑定具体显卡型号或音频设备。
- 默认使用 `hwdec=auto-safe`。
- 默认音频设备为 `auto`，声道为 `auto-safe`。
- 不提交播放历史、缓存、watch_later、弹幕历史和 token。

## 注意

本仓库通过 GitHub 连接器先上传了公开说明和通用核心配置。完整本地整理包仍保留在压缩包里，包含更多第三方脚本与 shader；公开同步时请继续保留上游许可证和 README。
