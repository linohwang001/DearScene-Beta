# DearScene Beta

しまっていた写真を、景色に。

DearSceneは、フォルダーに眠る写真と動画を選び、整え、静かにめぐらせるWindows向けローカルメディアディスプレイです。

## DearScene v1.23 Beta

- [紹介ページをブラウザで見る](https://linohwang001.github.io/DearScene-Beta/)
- [DearScene v1.23をダウンロード](https://github.com/linohwang001/DearScene-Beta/releases/download/v1.23-beta.1/DearScene-v1.23.exe)
- [意見・不具合をGoogle Formsで送る](https://forms.gle/5TT5WFhG5xzA45oW9)
- [v1.23 Betaのリリース情報](https://github.com/linohwang001/DearScene-Beta/releases/tag/v1.23-beta.1)

## 動作環境

- Windows 10／11 x64
- 写真・動画を保存したローカルドライブ、USB HDD、その他Windowsから参照できるフォルダー

## はじめ方

1. DearSceneをダウンロードして起動します。
2. 「フォルダーを追加」から、再生したい写真・動画が入った場所を選びます。
3. 表示方法、時間、写真と動画の合わせ方を選んで再生します。

DearSceneは元の写真・動画を移動・編集しません。ベータ版のため、大切なデータは必ず別途バックアップしてください。

## v1.23の安定性・安全対策

- 検証済み内蔵FFmpegだけを利用し、ビルド時・展開時・起動前にSHA-256を照合
- FFmpegの入力をローカルファイルとアプリ内パイプへ限定
- DLLをWindows System32からのみ読み込み、RAW内蔵プレビューは128MiBを上限に設定
- 分割表示用の短い互換動画を事前に準備し、長尺動画の全尺変換を待たずに全枠をライブ再生
- 動画デコーダーをページ間で安全に引き渡し、準備待ちを黒画面や停止として誤検出しない監視へ改善
- USB接続SSDの動画で4窓×短冊3分割（合計12動画）、3秒切替、各窓7回更新を実機確認。黒画面、迂回、静止画代替はいずれも0件

詳細は[リリースノート](RELEASE_NOTES_v1.23.md)、[セキュリティポリシー](SECURITY.md)、[ベータ利用条件](TERMS.md)を確認してください。

## フィードバック

個人の写真、個人名を含むフルパス、秘密情報は公開Issueへ添付しないでください。画像の添付が必要な場合は、[Google Forms](https://forms.gle/5TT5WFhG5xzA45oW9)をご利用ください。

## ファイル検証

配布ファイルのSHA-256は [MANIFEST_v1.23.txt](MANIFEST_v1.23.txt) に記載しています。現在のEXEはコード署名されていないため、GitHub Releases以外から入手したファイルは実行せず、次のコマンドで照合してください。

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\DearScene-v1.23.exe
```

一致しない場合は実行しないでください。組織管理PCのセキュリティ警告は回避せず、管理者へ確認してください。

## 完全に削除する

DearSceneを終了してEXEを削除します。設定、索引、履歴、内蔵ランタイム、互換動画プロキシも消す場合は`%LOCALAPPDATA%\DearScene`を削除してください。Windowsのアプリ別GPU設定は「設定 > システム > ディスプレイ > グラフィック」からDearSceneを削除できます。

Copyright © 2026 DearScene. All rights reserved.
