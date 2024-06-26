---
title: ハードウェア対応状況とロードマップ
tags:
  - Linux
  - U-Boot
  - 周辺機器
  - 沼の入り口
excerpt: Brainux が自分の電子辞書にどれくらい対応しているかチェックしたい人はこちら
---


# Linux のブート

|キーボードの世代|対応済|説明|
|:--|:-:|:--|
|3桁世代, G4000, G5000, G5100, A7000, A9000||TOSHIBA TMPA910CRAXBG|
|4桁世代, Sx1 〜 Sx7|:white_check_mark:|NXP i.MX283|
|x1||NXP i.MX7|


# キーボード

|キーボードの世代|対応済|説明|
|:--|:-:|:--|
|3桁世代||SoC が直接キーマトリックスを読む|
|4桁世代, Sx1 〜 Sx2|:white_check_mark:|MPU がキーマトリックスを読み SoC に I²C で送信|
|Sx3 〜 Sx7|:white_check_mark:|SoC が直接キーマトリックスを読む|
|x1||詳細不明||


# 画面開閉検知

- 開閉イベントの伝達はキーイベントと同じ経路をたどる
- キーボードの実装に依存する

|キーボードの世代|対応済|説明|
|:--|:-:|:--|
|3桁世代||SoC が直接キーマトリックスを読む|
|4桁世代, Sx1 〜 Sx2||MPU がキーマトリックスを読み SoC に I²C で送信|
|Sx3 〜 Sx7||SoC が直接キーマトリックスを読む|
|x1||詳細不明||


# 音

- Brain に内蔵されているスマートアンプには大きく分けて Yamaha 系と Rohm 系がある
- 録音と再生は2021年2月23日現在解析中で非対応


# タッチパネル

- 2021年2月23日現在反応はするが位置がおかしい
- 世代によるハードウェアの差分は不明


# 電源コントローラ

- 2021年2月23日現在未対応のため充電状態の表示などは一切不可


# cpufreq

- CPU のクロック制御は2021年2月23日現在なし


# eMMC への Linux インストール

- 研究中


# Wi-Fi

Wi-Fi の接続は複数の手法が提案されていて、現在検証中。

- SDIO Wi-Fi チップ
- USB ドングル


# LCD

一部については実装が完了。ただし、DMA を使用しない非効率な実装になっているため、改善が必要。

|世代|対応済み|
|:--|:-:|
|3桁世代||
|4桁世代|:white_check_mark:|
|Sx1 〜 Sx7|:white_check_mark:|
|x1||


# Brainux のリリース

当面は Development リリースや Stable リリースのような区分は設けず、[brain-hackers/buildbrain](https://github.com/brain-hackers/buildbrain) リポジトリのタグを直接バージョンとする。リリース間隔やスケジューリングも行わない。

