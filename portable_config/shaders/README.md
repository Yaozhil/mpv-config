# shaders

Shader 文件属于可选增强项，不建议默认强制启用。

公开通用版默认不绑定某张显卡，也不默认加载高负载 shader。用户可按自己的 GPU 性能，将需要的 `.glsl` 文件放入本目录，并在 `mpv.conf` 或 `input.conf` 中启用。

常用目录示例：

```text
portable_config/shaders/igv/
portable_config/shaders/Anime4K/
portable_config/shaders/nnedi3/
portable_config/shaders/ravu/
```

完整本地整理包中包含更多 shader 文件；公开同步时请注意保留原始许可证。
