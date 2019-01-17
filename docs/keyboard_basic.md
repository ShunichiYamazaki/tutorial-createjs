---
title: JavaScript でのキーボード制御
author: 池田 泰延
published_date: 2015-11-30
modified_date: 2018-02-20
---

### キーボードを押したとき

キーボードが押されたか調べるには、`keydown` イベントを使用します。登録した関数の引数からイベントオブジェクトが得られます。`window`オブジェクトに対してイベントを登録しましょう。

```js
window.addEventListener("keydown", handleKeydown);

function handleKeydown(event){
  console.log("キーボードが押された");
}
```

どのキーが押されたかについては`event`オブジェクトの情報からわかります。

```js
window.addEventListener("keydown", handleKeydown);

function handleKeydown(event){
  // キーコード
  var keyCode = event.keyCode;
  console.log("押されたキーのコード : " + keyCode);
}
```

### キーボードから離されたとき

キーボードが離されたかを調べるには`keyup`イベントを使用します。

```js
window.addEventListener("keyup", handleKeyup);

function handleKeyup(event){
  console.log("キーボードが離された");
}
```


## キーコードの判定

キーが押された時を判定するには、キーコードの数値を使って判定します。

```js
window.addEventListener("keydown", handleKeydown);

function handleKeydown(event){
  // キーコード(どのキーが押されたか)を取得
  var keyCode = event.keyCode;
  // 条件文で制御する
  if (keyCode == 39) {
    // 右
  }
  if (keyCode == 37) {
    // 左    
  }

  if (keyCode == 38) {
    // 上
  }
  if (keyCode == 40) {
    // 下
  }
}
```

キーコードの一覧表は次のページを参考にするといいでしょう。

- [各ブラウザのキーコード表[JavaScript]](https://web-designer.cman.jp/javascript_ref/keyboard/keycode/)

[次の記事へ](keyboard_ship.md)

