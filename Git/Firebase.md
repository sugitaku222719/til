# Firebase導入
- はじめに～firebase設定まで終了(20241007)  
- firebaseは、NoSQL型の開発
- database、本番環境の提供、ユーザーログイン機能などを提供している

# Firebase導入2
- ホスティング、データベース作成を行った  
- npm install -g firebase-toolsを実行することで、ターミナル上でFirebaseを動かすことができるようになる
-  npm i firebasでfirebaseのライブラリを取得

# データベースの取得
```js
const userRef = db.collection('users').doc('cTHCCZTUjcDzyy2RSMMj')
    const doc = await userRef.get()
    console.log('Document data:', doc.data());
    if (!doc.exists) {
      console.log('No such document!');
    } else {
      console.log('Document data:', doc.data());
    }
```
  
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

# データベースの更新
```js
const handleClickUpdateButton = async () => {
    const db = firebase.firestore();
    const userRef = db.collection('users').doc('cTHCCZTUjcDzyy2RSMMj');
    userRef.update({
      name:'新しい田中',
      age: 100
    });
  }
```

# データベースの削除
```js
const handleClickDeleteButton = async () => {
    const db = firebase.firestore();
    const userRef = db.collection('users').doc('cTHCCZTUjcDzyy2RSMMj');
    await userRef.delete();
  }
```

# データベースの検知
```js
useEffect(() => {
    const db = firebase.firestore();
    const unsubscribe = db.collection('users').onSnapshot((querySnapshot) => {
      console.log('検知！！！');
      querySnapshot.forEach(
        doc => {
          console.log(doc.id, doc.data());
          console.log('-----------');
        });
    });
    return () => {
      unsubscribe();　　　//onSnapshotをページ遷移のタイミングで止めている
    };
  }, []);
```
