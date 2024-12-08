# 配列分割代入
```js
const [N, M] = lines[0].split(' ').map(Number);
```
1つ目の要素をNに、２つ目の要素をMに代入.  
3つ目以降の要素はどこにも代入されない。2つ目の要素が無ければundefinedとなる.  

# Map()
```js
const shop = new Map();
shop.set("apple", 100);
shop.set("banana", 80);
console.log(shop.get("apple")); // 100
console.log(shop.has("orange")); // false
```
const shop = new Map(); は、JavaScriptで新しいMapオブジェクトを作成するための文です。この文について詳しく説明します：
Mapオブジェクトの特徴:
Mapは、キーと値のペアを保持するコレクションです。
各キーはMap内で一意であり、1回しか出現しません。
キーには任意のデータ型（オブジェクトや関数を含む）を使用できます。
Mapの利点:
挿入順序を記憶します。
キーの型に柔軟性があります（オブジェクトや関数もキーとして使用可能）。
サイズプロパティ（size）を持っています。
直接反復可能です。
Mapの主要なメソッド:
set(key, value): 新しいキーと値のペアを追加します。
get(key): 指定されたキーに関連付けられた値を取得します。
has(key): 指定されたキーが存在するかどうかをチェックします。
delete(key): 指定されたキーと関連する値を削除します。

# .map()
配列に対して、.map()を使用することで、各要素に対して関数を適用できる。例えば、
const array = [["a_1 a_2 a_3"],["b_1 b_2 b_3"],["c_1 c_2 c_3"]]
に対して、
const board = array.map(row => row.split(" "))
とすることで、
borad =  [["a_1","a_2","a_3"],["b_1","b_2","b_3"],["c_1","c_2"."c_3"]]
となる。  
二次元配列などを展開するときにも使用する。

# 配列に対する複数の要素の検索
if文を用いて、  
```js
if (board[i][j] == "#" && board[i][j+1] == "#" && board[i][j+2] == "#" && board[i+1][j] == "#" && board[i+1][j+1] == "." && board[i+1][j+2] == "#" && board[i+2][j] == "#" && board[i+2][j+1] == "#" && board[i+2][j+2] == "#"){
                count += 1;
}
```
のように記述するしかない。
