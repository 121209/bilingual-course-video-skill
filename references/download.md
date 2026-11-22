# 片源下载

## 先核对来源

- 以课程官方页面列出的视频为准，下载前核对 YouTube 视频 ID。
- 课件按官方地址保存。斯坦福 CS329Z 的课件形式为：`https://web.stanford.edu/class/cs329z/slides/lectureXX.pdf`（XX 为零补位讲次）。其他课程使用该课程自己的官方课件链接。
- 课程主页（CS329Z 为 https://cs329z.stanford.edu/）和课件 HTML / PDF 一并保存。
- 若该讲有官方 notebook 或代码仓库，一并保存，翻译专有名词时要对照。

## 视频与官方字幕

使用 `yt-dlp` 下载 1080p AVC 视频 + 原声英文 AAC，并下载官方英文字幕。不要自动字幕，也不要先上 Whisper（无官方 CC 时再和用户商量）。

优先选择 1080p AVC 画面，外加原声英文 AAC（不要下到翻译或配音音轨）。若某条格式代码不可用，改选最佳 1080p AVC + 原声英文 AAC。官方 CC 轨道 ID 可能因视频而异，选择官方 English CC，不要 auto-captions。

示例：

```bash
yt-dlp -f "137+140-20" \
  --write-subs --sub-langs "en-j3PyPqV-e1s" --convert-subs srt \
  -o "<work>/src/lectureXX_source.%(ext)s" \
  "YOUTUBE_URL"
```

上面的格式代码和字幕轨道名来自部分 CS329Z 讲次的实际情况（137：1080p AVC；140-20：AAC 128 kb/s 英文原声）。其他视频先探测可用格式，再按同样原则选择。

下载后用 ffprobe 核对。常见情况为 1920×1080、29.97 fps、h264 yuv420p、AAC 44.1 kHz 立体声约 128 kb/s。成片时长须与片源一致（允许与来源标称差 1 秒内）。

课件 PDF 与课程页放入 `src/slides/`、`src/`。
