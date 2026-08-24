# DearScene Beta

しまっていた写真を、景色に。

DearSceneは、フォルダーに眠る写真と動画を選び、整え、静かにめぐらせるWindows向けローカルメディアディスプレイです。

## DearScene v1.3 Beta

- [紹介ページをブラウザで見る](https://linohwang001.github.io/DearScene-Beta/)
- [DearScene v1.3をダウンロード](https://github.com/linohwang001/DearScene-Beta/releases/download/v1.3-beta.1/DearScene-v1.3.exe)
- [意見・不具合をGoogle Formsで送る](https://forms.gle/5TT5WFhG5xzA45oW9)
- [v1.3 Betaのリリース情報](https://github.com/linohwang001/DearScene-Beta/releases/tag/v1.3-beta.1)

## 動作環境

- Windows 10／11 x64
- 写真・動画を保存したローカルドライブ、USB HDD、その他Windowsから参照できるフォルダー

## はじめ方

1. DearSceneをダウンロードして起動します。
2. 「フォルダーを追加」から、再生したい写真・動画が入った場所を選びます。
3. 表示方法、時間、写真と動画の合わせ方を選んで再生します。

DearSceneは元の写真・動画を移動・編集しません。ベータ版のため、大切なデータは必ず別途バックアップしてください。

## v1.3の新機能・安定性

- 検証済み内蔵FFmpegだけを利用し、ビルド時・展開時・起動前にSHA-256を照合
- FFmpegの入力をローカルファイルとアプリ内パイプへ限定
- DLLをWindows System32からのみ読み込み、RAW内蔵プレビューは128MiBを上限に設定
- 「メイソンリー：貴金属比」と「メイソンリー：元の比率を維持」を選択可能
- 最終的な枠の向きに合わせて、縦作品を縦枠、横作品を横枠へ優先配置
- 複数表示用動画は、対応環境でGPUデコードと選択GPUによるH.264変換を優先
- 分割表示用の短い互換動画を事前に準備し、長尺動画の全尺変換を待たずに全枠をライブ再生
- 長尺動画を再生中の映像進行として判定し、写真用の期限やループを停止と誤認しない監視へ改善
- 次ページの動画が実際に動き始めるまで現在ページをライブ再生し、全画面でも停止や黒画面を見せずに切り替え
- USB接続ドライブの縦動画3本・横動画2本で、両メイソンリー方式を各6ページ実機確認。全枠5/5が進行し、縦横不一致、黒画面、迂回、再同期はいずれも0件

詳細は[リリースノート](RELEASE_NOTES_v1.3.md)、[実機試験報告](TEST_REPORT_v1.3.md)、[セキュリティポリシー](SECURITY.md)、[ベータ利用条件](TERMS.md)を確認してください。

## フィードバック

個人の写真、個人名を含むフルパス、秘密情報は公開Issueへ添付しないでください。画像の添付が必要な場合は、[Google Forms](https://forms.gle/5TT5WFhG5xzA45oW9)をご利用ください。

## ファイル検証

配布ファイルのSHA-256は [MANIFEST_v1.3.txt](MANIFEST_v1.3.txt) に記載しています。現在のEXEはコード署名されていないため、GitHub Releases以外から入手したファイルは実行せず、次のコマンドで照合してください。

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\DearScene-v1.3.exe
```

一致しない場合は実行しないでください。組織管理PCのセキュリティ警告は回避せず、管理者へ確認してください。

## 完全に削除する

DearSceneを終了してEXEを削除します。設定、索引、履歴、内蔵ランタイム、互換動画プロキシも消す場合は`%LOCALAPPDATA%\DearScene`を削除してください。Windowsのアプリ別GPU設定は「設定 > システム > ディスプレイ > グラフィック」からDearSceneを削除できます。

Copyright © 2026 DearScene. All rights reserved.
