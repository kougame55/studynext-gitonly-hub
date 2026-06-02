# StudyNext Firebase Hub

Google Sites の「URL埋め込み」で使える StudyNext Hub です。
Firebase Auth + Firestore で、児童ポータル・先生ポータル・学習アプリ・デジタルプリントを同じStudyNextアカウントで連携します。

## 公開URL

- 児童ポータル: `https://kougame55.github.io/studynext-gitonly-hub/`
- 先生ポータル: `https://kougame55.github.io/studynext-gitonly-hub/teacher.html`
- Google Sites用コピー画面: `https://kougame55.github.io/studynext-gitonly-hub/google-sites-deploy.html`
- Firebase Auth診断: `https://kougame55.github.io/studynext-gitonly-hub/firebase-auth-check.html`

## Google Sitesへの貼り方

1. Google Sitesを開く
2. `挿入`
3. `埋め込む`
4. `URL`
5. 児童ポータルまたは先生ポータルのURLを貼る

HTMLコードで貼る場合は、`google-sites-deploy.html` の iframe コードをコピーして使います。

## Files

- `index.html` / `google-sites-embed.html`: 児童用ポータル
- `teacher.html`: 先生用ポータル
- `google-sites-deploy.html`: Google Sites用URL/iframeコピー画面
- `apps/speed.html`: SPEED算数
- `apps/kanji.html`: 漢字スプリント
- `apps/english.html`: 英単語リンク
- `apps/science.html`: 理科クイズラボ
- `apps/social.html`: 社会タイムライン
- `apps/typing.html`: タイピング道場
- `firestore.rules`: Firestoreセキュリティルール

## Firebase Data

- `users`: 個人/先生/学校アカウントのプロフィール
- `classes`: 先生が作成したクラス
- `invites`: 招待コード
- `classes/{classId}/students`: 招待コードから参加した児童
- `usageLogs`: どの児童が、どのアプリを、いつ、何分使ったか
- `messages`: 先生から児童への連絡とアンケート
- `replies`: 児童からの返信
- `surveyResponses`: アンケート回答
- `apps`: 先生が追加したアプリ
- `printAssignments`: 先生が配るデジタルプリント
- `printSubmissions`: 児童のプリント提出

## 追加済み機能

- Google Sites向けにアプリ起動URLを絶対URL化
- 児童ポータル設定タブにGoogle Sites埋め込みURLコピーを追加
- 児童ポータル設定タブに最近の学習履歴を追加
- 先生ポータルでデジタルプリント配信と提出確認
- 児童ポータルで配布されたプリントへの記入と提出

## Firebase Consoleで必要な設定

- Authentication画面で `始める` を押す
- Authentication: Email/Password
- Authentication: Google
- Authentication: Anonymous
- Firestore Database
- Authorized domains: `kougame55.github.io`

`auth/configuration-not-found` が出る場合は、Authentication自体がまだ開始されていません。
Firestoreルール反映だけではログインは動かないため、Firebase ConsoleでAuthenticationを開始してください。
