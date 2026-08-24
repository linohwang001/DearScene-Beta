# Security Policy

## 対応対象

現在は最新のDearScene Betaのみをセキュリティ更新の対象とします。古いベータ版で問題を確認した場合は、まず最新のプレリリースで再現するか確認してください。

## 非公開で報告する

脆弱性、任意コード実行、配布ファイルの改ざん、個人情報の露出につながる内容は公開Issueへ書かず、GitHubの[非公開脆弱性報告](https://github.com/linohwang001/DearScene-Beta/security/advisories/new)を利用してください。再現に個人の写真が必要な場合は、人物、住所、個人名、端末内のフルパスを伏せた最小限のサンプルに置き換えてください。

通常の不具合や使用感は[Google Forms](https://forms.gle/5TT5WFhG5xzA45oW9)へ送信できます。パスワード、APIキー、Cookie、秘密鍵はどちらにも送信しないでください。

## 配布ファイルの確認

DearSceneの実行ファイルは、GitHub Releasesからのみ入手してください。各リリースの `MANIFEST` に記載されたSHA-256と、ダウンロード後のファイルを照合できます。

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\DearScene-v1.23.exe
```

値が1文字でも異なる場合は実行せず、ファイルを削除して公式リリースから再取得してください。

## ローカル完結の境界

DearScene本体にはネットワーク通信、テレメトリ、自動更新機能がありません。FFmpegは固定した内蔵版だけを利用し、ハッシュが一致しない展開済みコピーは起動前に正規コピーへ置き換えます。FFmpegへ渡す入力プロトコルもローカルファイルとアプリ内パイプに限定します。
