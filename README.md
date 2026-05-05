# 鍵山製パン オーディオルーティングシステム

オーディオルーティングの構成図および設定情報をまとめたリポジトリです。

## システム構成図

![Audio Routing System](doc/system.svg)

## 概要

RME Babyface Pro FS をオーディオインターフェースのコアに据え、配信・収録・モニタリングを目的としたオーディオルーティングを構築しています。Reaper を中心に、各種ソフトウェア入出力（Discord、Notion など）とハードウェア入出力を柔軟にルーティングします。

## ハードウェア構成

| 種別                       | 機材                           | 用途                             |
| -------------------------- | ------------------------------ | -------------------------------- |
| オーディオインターフェース | RME Babyface Pro FS            | オーディオルーティングのコア     |
| マイク                     | SHURE BETA 58A                 | 音声入力                         |
| ヘッドホン                 | Moondrop 楽園 - PARA2          | モニタリング                     |
| スピーカー                 | YAMAHA HS5 W                   | モニタリング                     |
| DAC                        | TOPPING DX5 Ⅱ                  | DA変換とヘッドホン出力用アンプ   |
| キャプチャユニット         | AverMedia LIVE GAMER EXTREME 3 | ゲーム機等の映像・音声キャプチャ |

## ソフトウェアルーティング

主要な仮想入出力：

- **PC Default Output** — システム標準出力
- **Discord Input / Output** — Discordの入出力
- **Notion Input** — Notion AIノートへの入力
- **Reaper** — 音声処理

## チャンネルマッピング

RME Babyface Pro FS のチャンネル割り当て：

| カテゴリ          | 使用チャンネル                                              | 説明                           |
| ----------------- | ----------------------------------------------------------- | ------------------------------ |
| HARDWARE INPUTS   | AN 1(マイク) / Instr. 3/4(キャプチャ)                       | 入力端子のチャンネル           |
| SOFTWARE PLAYBACK | AN 1/2(音声用) / ADAT 3/4(PC再生音) / ADAT 5/6(Discord出力) | PC内部の音が流れるチャンネル   |
| HARDWARE OUTPUTS  | AS 1/2(DAC→ヘッドホン) / AN 1/2(スピーカー)                 | 出力端子のチャンネル           |
| CONTROL ROOM      | —                                                           | ヘッドホン出力端子のチャンネル |

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
