# Firebase導入
- はじめに～firebase設定まで終了(20241007)  
- firebaseは、NoSQL型の開発
- database、本番環境の提供、ユーザーログイン機能などを提供している

# Firebase導入2
- ホスティング、データベース作成を行った  
- npm install -g firebase-toolsを実行することで、ターミナル上でFirebaseを動かすことができるようになる
-  npm i firebasでfirebaseのライブラリを取得

# データベースの追加
```js
.collection(コレクション名).add({
キー: バリュー
キー:バリュー
})

.collection(コレクション名).doc(ドキュメントid).add({
キー: バリュー
キー:バリュー
})
```

という形で記述する。  
setはドキュメントidを指定して追加もしくは上書きするというもので、フィールドを追加したい場合はmerge: tureを第二引数に指定する。  
addはidを自動で生成し、追加する。
