# StudyNext Hub External Login

Cloudflareなし / GASなし / Google Sites埋め込み用のStudyNext Hubです。

## 公開URL

- https://kougame55.github.io/studynext-gitonly-hub/

## 外部ログインAPI

- API: https://066d0cc8fddf1a.lhr.life
- GitHub private DB: kougame55/studynext-private-db / studynext-users.json
- GitHubトークンはブラウザへ出さず、このPCのNode APIだけが使用します。

## デスクトップの操作ファイル

- `StudyNext_GoogleSites_貼り付け_外部ログイン版.html` をGoogle Sitesへ貼り付け
- `StudyNext_外部ログインAPI_起動.cmd` でAPIとトンネルを起動
- `StudyNext_外部ログインAPI_停止.cmd` で停止
- `StudyNext_GitOnly_更新.cmd` でGitHub Pagesを更新

## アプリ追加

1. `apps/*.html` を追加
2. `apps.json` に登録
3. `StudyNext_GitOnly_更新.cmd` を実行

SPEED算数は、点対称などの「はい/いいえ」問題でキーパッドが出ないように、答えが純粋な数字のときだけ入力式へ切り替えます。
