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
