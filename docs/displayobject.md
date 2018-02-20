# CreateJS の表示オブジェクト

CreateJSではステージに表示オブジェクトを追加することでコンテンツを作っていきます。例えば、舞台の演劇を想像してみましょう。ステージに役者が登場して演目が披露されますが、CreateJSのステージと役者の関係も同じです。ステージとはその名の通り`createjs.Stage`が、役者は表示オブジェクト`createjs.DisplayObject`になります。

表示オブジェクト`createjs.DisplayObject`をプログラムで直接使うことはほとんどありません。なぜなら、表示オブジェクトは実態を持っていることがほとんどで、シェイプ・画像・テキストの3種類で使うことが多いからです。まずはシェイプを例に表示オブジェクトについて紹介します。

まずは役者を用意します。

```js
var object = new createjs.Shape();
object.graphics.beginFill("DarkRed");
object.graphics.drawCircle(0, 0, 100);
```

このままでは役者はステージに登壇していないので、表示されません。表示させるためにはステージに登壇させる必要があります。プログラムでは`addChild()`という命令を使います。

```js
stage.addChild(object);
```

## 配置座標

ステージ上の役者の配置場所を指示しなければ、ステージの原点位置にしかいません。CreateJSにはX軸(水平)とY軸(垂直)の二軸があります。`.x`と`.y`という形でドットをつなげて配置座標を指定します。

```js
object.x = 100;
object.y = 100;
```

## 角度

`.rotation`で角度を指定することができます。角度は0度〜360度で一週を示します。

```js
object.rotation = 45; // 45度傾ける
```

## 透明度

`.alpha`で透明度を設定することができます。1.0が通常の状態(100%見える状態)で、0.0が完全に透明な状態(0%見える状態)です。

```js
object.alpha = 0.5; // 50%の透明度に設定する
```

## 表示/非表示

`.visible`で可視性を設定することができます。`true`が通常の状態(表示状態)で、`false`が非表示になった状態です。

```js
object.visible = false; // 非表示にする
```


## スケール

`.scaleX`や`.scaleY`で大きさを相対的に設定することができます。1.0が等倍で、倍率を数値で指定します。

```js
object.scaleX = 0.5; // 50%の幅に設定する
object.scaleY = 2.0; // 200%の高さに設定する
```

[次の記事へ](shape_fill_stroke.md)


<article-author>[池田 泰延](https://twitter.com/clockmaker)</article-author>
<article-date-published>2015-11-29</article-date-published>
<article-date-modified>2018-02-20</article-date-modified>
