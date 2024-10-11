# React
- React.jsとは、javascriptのフレームワーク  
- Node.jsというもので動かしている
- パワーシェル上で"npx create-react-app アプリ名"を実行することでアプリケーションを作成できる。
- パワーシェル上で"npm start"を実行することで、localhost3000を立ち上げることができる

# .map()、アロー関数
```js
const array1 = [1, 4, 9, 16];

// Pass a function to map
const map1 = array1.map((x) => x * 2);

console.log(map1);
// Expected output: Array [2, 8, 18, 32]
```

# .push
```js
const animals = ['pigs', 'goats', 'sheep'];

const count = animals.push('cows');
console.log(count);
// Expected output: 4
console.log(animals);
// Expected output: Array ["pigs", "goats", "sheep", "cows"]

animals.push('chickens', 'cats', 'dogs');
console.log(animals);
// Expected output: Array ["pigs", "goats", "sheep", "cows", "chickens", "cats", "dogs"]
```

# userコレクションを全て表示
```js
const userListItems = users.map(user => {
    return(
      <li key={user.userId}> 
        <ul>
          <li>ID : {user.userId}</li>
          <li>name : {user.name}</li>
          <li>age : {user.age}</li>
          <li>location : {user.location}</li>
        </ul>
       </li>
    );
  });
<ul>{userListItems}</ul>
```

# useEffect
```js
useEffect(() => { ... }, []);:
```
useEffect フックは、コンポーネントのレンダリング後に副作用を実行します。
[] の依存配列が空であるため、このエフェクトはコンポーネントの初回マウント時に一度だけ実行されます。  
[]に変更があった際に副作用が実行されます。  
  
```js
useEffect(() => {
  // 副作用の処理
  console.log('Effect is executed.');

  return () => {
    // クリーンアップの処理
    console.log('Cleanup is executed.');
  };
}, []);
```

コンポーネントの初回マウント時:  
console.log('Effect is executed.') が実行されます。  
コンポーネントのアンマウント時:  
返されたクリーンアップ関数が実行され、console.log('Cleanup is executed.') が実行されます。  
