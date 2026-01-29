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
- 長さ：1時間 or 30分
- 再生時間との誤差：１秒いかない程度

---
--- 
## ffmpeg がある人向け（生成コマンド） ### 1時間版（00:00:00 → 01:00:00）
bash
ffmpeg -f lavfi -i "color=c=black:s=1920x1080:r=30" -t 3600 \
-vf "drawtext=fontfile=/System/Library/Fonts/Supplemental/Arial.ttf:fontsize=160:fontcolor=white:x=(w-text_w)/2:y=(h-text_h)/2:text='%{pts\:hms}'" \
-c:v libx264 -pix_fmt yuv420p -movflags +faststart countup_60m.mp4
---

## ダウンロード / Download

Google Drive からダウンロードできます：  
You can download it from Google Drive:

[Google Drive フォルダ](https://drive.google.com/drive/folders/10SRCK4P1MjYgY6qbuw_6Ou6FQ326SPKw?usp=drive_link)


