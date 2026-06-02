# StudyNext Firebase Hub

Google Sites に URL 埋め込みできる、Firebase Auth + Firestore 版の StudyNext Hub です。

## Files

- `index.html` / `google-sites-embed.html`: 児童用ポータル
- `teacher.html`: 先生用ポータル
- `apps/speed.html`: SPEED算数
- `apps/kanji.html`: 漢字スプリント
- `apps/english.html`: 英単語リンク
- `apps/science.html`: 理科クイズラボ
- `apps/social.html`: 社会タイムライン
- `apps/typing.html`: タイピング道場
- `firestore.rules`: Firestore セキュリティルール雛形

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

## Current Firebase Check

Firebase SDK `12.14.0` は読み込み確認済みです。
ただし、このプロジェクトは現時点で Firebase Authentication が未初期化のため、メール/匿名ログインは `auth/configuration-not-found` になります。

Firebase Console で以下を有効化すると、HTML側のログインが動きます。

- Authentication: Email/Password
- Authentication: Google
- Authentication: Anonymous
- Firestore Database

## Google Sites

公開 URL を Google Sites の「埋め込み > URL」に入れて使います。

SPEED算数は、点対称などの「はい/いいえ」問題でキーパッドが出ないように、答えが純粋な数字のときだけ入力式へ切り替えます。

## Digital Print

先生ポータルの「デジタルプリント」で課題を配信します。
児童ポータルの「プリント」に届き、児童は配られた課題へ記入して提出します。
児童から自由にカードを作成する機能は入れていません。
