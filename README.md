# one-hour-countup-video
A simple 1-hour count-up timer video (HH:MM:SS), generated with ffmpeg.

# 1時間カウント（HH:MM:SS）動画

「**1時間を秒までカウントアップするだけ**」のシンプルな動画です（00:00:00 → 01:00:00）。

撮影現場のタイムキープ、配信の尺管理、開発中の動作確認（タイマー表示・同期テスト）など、**“とりあえず1時間のカウント動画が欲しい”**場面でそのまま使えます。  
必要になった時に **ご自由にお使いください**。

- 背景：黒
- 文字：白
- 表示形式：HH:MM:SS（カウントアップ）
- 解像度：1920x1080 / 30fps
- 長さ：1時間

---

## 使い方（動画をそのまま使う）

このリポジトリに同梱している動画、もしくは Releases に置いた動画をダウンロードして使ってください。

> ※ GitHub は大きな動画ファイルの管理に向かないことがあるので、公開する場合は **Releases** に置く運用がおすすめです。

---

## ffmpeg がある人向け（生成コマンド）

### 1時間版（00:00:00 → 01:00:00）
```bash
ffmpeg -f lavfi -i "color=c=black:s=1920x1080:r=30" -t 3600 \
-vf "drawtext=fontfile=/System/Library/Fonts/Supplemental/Arial.ttf:fontsize=160:fontcolor=white:x=(w-text_w)/2:y=(h-text_h)/2:text='%{pts\:hms}'" \
-c:v libx264 -pix_fmt yuv420p -movflags +faststart countup_60m.mp4
```

---

## English version (for README)
# 1-Hour Count-Up (HH:MM:SS) Video

A simple video that **counts up for one hour down to the second** (00:00:00 → 01:00:00).

Use it as-is whenever you just need a **one-hour count-up timer video**—for on-set timekeeping, stream duration management, or development/testing (timer UI checks, sync tests, etc.).  
Feel free to use it whenever you need it.

- Background: Black
- Text: White
- Format: HH:MM:SS (count-up)
- Resolution: 1920x1080 @ 30fps
- Duration: 1 hour

---

## How to Use (Use the Video As-Is)

Download and use the video included in this repository, or grab it from the Releases page.

> Note: GitHub isn't always ideal for hosting large video files. If you publish the video, it’s recommended to put it in **Releases**.

---

## For People with ffmpeg (Generation Command)

### 1-hour version (00:00:00 → 01:00:00)

```bash
ffmpeg -f lavfi -i "color=c=black:s=1920x1080:r=30" -t 3600 \
-vf "drawtext=fontfile=/System/Library/Fonts/Supplemental/Arial.ttf:fontsize=160:fontcolor=white:x=(w-text_w)/2:y=(h-text_w)/2:text='%{pts\:hms}'" \
-c:v libx264 -pix_fmt yuv420p -movflags +faststart countup_60m.mp4
```
