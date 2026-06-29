# 发布前检查

## 推荐发布形态

- Git 仓库：README、功能说明、展示图、清洁配置样例。
- Release/网盘附件：完整便携整合包 ZIP。
- 公开清洁版依据：ZIP 内的 `dist/mpv-config-release/`。

## 当前整合包

```text
C:\Users\杳知\Desktop\mpv（杳知整合包）6.29.zip
```

该 ZIP 顶层包含完整便携播放器和运行目录，更适合作为下载包。仓库同步时应优先取 `dist/mpv-config-release/`，避免把运行缓存和大型二进制直接写入 Git。

## 必查项目

- `portable_config/files/`：不应发布个人播放历史、弹幕历史、最近播放、日志。
- `portable_config/cache/`：不应发布 watch_later、shader cache。
- `script-opts/file_browser_alist.conf`：公开版应清空 `host`、`username`、`password`。
- `script-opts/skip_segments.conf`：公开版不应携带个人 TMDb key。
- `script-opts/trakt_scrobble.conf`：公开版不应携带 Trakt client secret。
- `mpv.conf`：不应绑定本机 GPU、音频设备或绝对路径。

## 已确认

- 桌面 `mpv_config` 中的 `file_browser_alist.conf` 已清空地址、账号和密码。
- ZIP 内的 `dist/mpv-config-release/` 未发现运行历史、日志、watch_later、shader cache 或网盘凭据。
- ZIP 顶层仍包含完整便携播放器、缓存和历史类文件，因此不建议直接作为仓库内容提交。
