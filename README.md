# 鍵山製パン オーディオルーティングシステム

オーディオルーティングの構成図および設定情報をまとめたリポジトリです。

## システム構成図

![Audio Routing System](doc/system.svg)

## 概要

RME Babyface Pro FS をオーディオインターフェースのコアに据え、配信・収録・モニタリングを目的としたオーディオルーティングを構築しています。Reaper を中心に、各種ソフトウェア入出力（Discord、Notion など）とハードウェア入出力を柔軟にルーティングします。

## ハードウェア構成

| 種別                       | 機材                           | 用途                         |
| -------------------------- | ------------------------------ | ---------------------------- |
| オーディオインターフェース | RME Babyface Pro FS            | オーディオルーティングのコア |
| マイク                     | SHURE BETA 58A                 | 音声入力                     |
| ヘッドホン                 | Moondrop 楽園 - PARA2          | モニタリング                 |
| スピーカー                 | YAMAHA HS5 W                   | モニタリング                 |
| DAC                        | TOPPING DX5 Ⅱ                  | デジタル/アナログ変換        |
| キャプチャユニット         | AverMedia LIVE GAMER EXTREME 3 | 映像・音声キャプチャ         |

## ソフトウェアルーティング

主要な仮想入出力チャンネル：

- **Discord Input / Output** — ボイスチャット入出力
- **Notion Input** — 通話入力
- **PC Default Output** — システム標準出力
- **Loopback** — 内部ルーティング用ループバック
- **Gachikoe** — 音声処理チャンネル

## 信号処理

Reaper 上で以下のプラグイン処理を適用：

- **iZotope RX8 De-ess** — 歯擦音除去
- **iZotope RX8 Voice De-noise** — ノイズ除去

## チャンネルマッピング

RME Babyface Pro FS のチャンネル割り当て：

| カテゴリ          | チャンネル                              | 説明                           |
| ----------------- | --------------------------------------- | ------------------------------ |
| HARDWARE INPUTS   | Mic / Instr. 3/4 / AS 1/2               | 入力端子のチャンネル           |
| SOFTWARE PLAYBACK | AN 1/2 / ADAT 3/4 / ADAT 5/6 / ADAT 7/8 | PC内部の音が流れるチャンネル   |
| HARDWARE OUTPUTS  | AN 1 など                               | 出力端子のチャンネル           |
| CONTROL ROOM      | —                                       | ヘッドホン出力端子のチャンネル |

## ファイル構成

```
.
├── README.md
└── doc/
    ├── system.drawio   # 構成図ソース（draw.io）
    ├── system.svg      # 構成図 SVG 形式
    └── system.png      # 構成図 PNG 形式
```

## 構成図の編集

構成図は [draw.io](https://app.diagrams.net/) で編集できます。`doc/system.drawio` を開いて編集後、SVG 形式でエクスポートしてください。
