# StudyNext GitHub Private DB Hub

Google Sites の「URL埋め込み」で使える StudyNext Hub です。
Firebase は使わず、GitHub private repo をDBとして使い、このPCで起動する Node API が安全に読み書きします。

## 公開URL

- 児童ポータル: `https://kougame55.github.io/studynext-gitonly-hub/`
- 先生ポータル: `https://kougame55.github.io/studynext-gitonly-hub/teacher.html`
- Google Sites貼り付けキット: `https://kougame55.github.io/studynext-gitonly-hub/google-sites-deploy.html`

## Google Sites への貼り方

1. Google Sites を開く
2. `挿入`
3. `埋め込む`
4. `URL`
5. 児童ポータルまたは先生ポータルのURLを貼る

HTMLコードで貼る場合は `google-sites-deploy.html` の iframe コードをコピーします。

## 重要

- GitHubトークンはHTMLに入れていません。API側だけが private repo に書き込みます。
- このPCのAPIと公開トンネルが動いている間だけログイン・保存できます。
- PCをスリープ、再起動、ネット切断するとAPIが止まります。
- トンネルURLが変わった場合は `external-api/publish-api-url.js` でHTMLへ反映し、再公開します。
- Firebase とクレカ登録は不要です。

## Files

- `index.html` / `google-sites-embed.html`: 児童用ポータル
- `teacher.html`: 先生用ポータル
- `google-sites-deploy.html`: Google Sites用URL/iframeコピー画面
- `apps/speed.html`: SPEED算数
- `apps/kanji.html`: 漢字スプリント
- `apps/english.html`: English Dash
- `apps/science.html`: 理科フラッシュ
- `apps/social.html`: 社会クイズ
- `apps/typing.html`: タイピング道場

## GitHub private DB Data

- `users`: 個人・先生・学校アカウント
- `classes`: 先生が作成したクラス
- `invites`: 招待コード
- `studentIds`: 招待コードから参加した児童ID
- `usageLogs`: どの児童が、どのアプリを、いつ、何分使ったか
- `messages`: 先生から児童への連絡とアンケート
- `replies`: 児童からの返信
- `surveyResponses`: アンケート回答
- `apps`: 先生が追加したアプリ
- `printAssignments`: 先生が出すデジタルプリント
- `printSubmissions`: 児童のプリント提出

## API起動

```powershell
cd C:\Users\user\Documents\Codex\2026-06-02\giga-pc-googlesite-html\external-api
node server.js
```

外部公開URLは `localhost.run` トンネルで発行し、`publish-api-url.js` でHTMLへ反映します。
