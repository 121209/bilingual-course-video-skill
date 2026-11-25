# 压制与质检

## 压制参数

在用户确认字号样例之后，再压制完整成片。参考命令：

```bash
ffmpeg -y -i "$SRC" \
  -vf "ass=${ASS}:fontsdir=/usr/share/fonts/opentype/noto" \
  -c:v libx264 -profile:v high -pix_fmt yuv420p -preset fast -crf 19 \
  -c:a copy \
  -r 30000/1001 \
  -metadata title="COURSE Lecture N - <原标题>" \
  -movflags +faststart \
  "$OUT"
```

- 只使用 `ass` 滤镜烧录字幕。不要加 `pad`，不要把画布做成 1920×1280，禁止 `pad=1920:1280:0:0:black`。
- 视频：libx264 High、yuv420p、CRF 19、preset fast。
- 音频：`copy` 原英文音轨，禁止重编码或配音。
- 帧率：若片源是 30000/1001，跟随之；其他帧率不要无故改掉。
- 分辨率：与片源一致，默认 1920×1080，完整 16:9，不缩放、不裁切，四边不加黑边。
- 已有成片不要直接覆盖，先备份。

字体目录按本机 Noto Sans CJK 的实际路径调整。若本机没有该字体，先安装或改用等价的 Noto Sans CJK SC，不要换成会明显改变中文宽度的字体。

## 质检清单

1. 对照课件完成翻译与术语对齐。
2. 按已确认字号生成 ASS（`PlayResX=1920`，`PlayResY=1080`），检查无 5 行 cue，并列出所有英文小于约定字号的条目及实际字号。
3. 先做短样例（建议覆盖：幻灯 2 行 / 4 行，出镜 2 行 / 3 行 / 4 行，如有代码或 Keynote 也要有一帧）。样例必须是完整 16:9、默认 1920×1080、无黑边，送给用户确认。
4. 用户确认后再压制完整成片。
5. 成片质检：
   - 时长与片源一致（允许与来源标称差 1 秒内）；
   - `silencedetect`（−40 dB，最短 2.5 s）不应出现讲中异常静音（片头片尾静音除外）；
   - 成片为 16:9 / 1920×1080，四边没有额外黑边；抽帧确认字幕在画面内底部，未挡住幻灯正文、代码、页脚和脸；滤镜未使用 `pad=1920:1280`；
   - 音画与官方 CC 起止对齐。
6. 同时交付：`bilingual.ass`、中英 / 双语 SRT 与 JSON、`qc-report.md`、投稿文案 `posting.md`。
