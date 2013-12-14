Theta Viewer
============

RICOH THETAのような正距円筒図法(Equirectangular Projection)のパノラマ画像を、WebでブラウズできるHTML5ビューアーです。
[jQuery](http://jquery.com/)のプラグインになっています。
描画にはJavaScriptによる3Dライブラリ[three.js](http://threejs.org/)を使用しています。

Setup
-------------

1. jQueryとthree.jsをHTMLに先に読み込みます。以下の例は、jQueryとthree.jsをダウンロードし、jsフォルダに置いた場合のものになっています。
2. Theta ViewerをHTMLに読み込みます。以下の例は、配布しているファイルの中のbuildフォルダ中のtheta-viewer.min.jsをjsフォルダに置いた場合のものになっています。
3. HTMLのbody要素の中にTheta Viewerでパノラマ画像を表示する要素(例では#theta-viewer)を用意します。
4. 画像ファイルURLや初期カメラ位置、傾き補正のための値などは、パノラマ画像の表示要素の属性として与えます。
5. パノラマ画像を表示するコードを記述します。具体的には「jQuery(パノラマ画像を表示したいセレクタ).createThetaViewer();」で表示できます。以下の例では、#theta-viewerにimgフォルダの中のtheta.jpgを表示しています。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <script src="js/jquery-1.10.2.min.js"></script>
  <script src="js/jquery-migrate-1.2.1.min.js"></script>
  <script src="js/three.min.js"></script>
  <script src="js/theta-viewer.min.js"></script>
  <link rel="stylesheet" href="css/styles.css">
  <title>Sample of THETA Viewer</title>
</head>
<body>
  <div id="theta-viewer" data-image="img/theta.jpg" data-zenith-x="-3.0" data-zenith-y="2.0" data-azimuth="270" data-elevation="-10"></div>
  <script>
/*global jQuery */
(function ($) {
    'use strict';
    $("#theta-viewer").createThetaViewer();
}(jQuery));
  </script>
</body>
</html>
```

Attributes
----------

- data-image    : 表示したい画像のURL
- data-zenith-x : 天頂の傾きのX成分(度)
- data-zenith-y : 天頂の傾きのY成分(度)
- data-azimuth  : カメラの初期方位(度)
- data-elevation: カメラの初期仰角(度)

天頂の傾き情報はTHETAが出力する画像ファイルに書き込まれています。[ここ](http://d.hatena.ne.jp/xanxys/20131110/1384094832)に掲載されている Python スクリプトで出力される zenith\_x, zenith\_y の値を data-zenith-x, data-zenith-y に与えてください。

Manipulation
------------

- マウスのドラッグで注視点を移動
- マウスのホイールでズームイン/ズームアウト

Samples
-------

* [サンプル1(画像を指定して読み込み)](http://akokubo.github.io/ThetaViewer/demo1.html)
* [サンプル2(画像をドラッグ&ドロップ)](http://akokubo.github.io/ThetaViewer/demo2.html)

Platforms
---------

- Chrome
- Safari
- Firefox
- Internet Explorer 11
- 対応したい: iOS、Android

Problems
--------

- OS X MarvericksでFirefox v.25の場合(他の環境では未確認)、スクロールによりウィンドウ内外にTheta Viewerコンテンツを移動するとハングする。three.jsのWebGLRendererを使用してアニメーションを実行しているためだと思われる。

ChangeLogs
----------

- v.0.3.0 2013/12/14 傾き補正・カメラ初期位置を設定可能にした
- v.0.2.0 2013/11/12 同一ページ内に複数のTheta Viewerコンテンツが存在できるように修正
- v.0.1.2 2013/11/11 画像が裏表逆に表示されるのを修正
- v.0.1.1 2013/11/10 マウス操作のバグを修正
- v.0.1 2013/11/08 リリース


License
-------

MIT License

Author
------

[小久保温(Atsushi Kokubo)](http://www.dma.aoba.sendai.jp/~acchan/).
[Kentaro Fukuchi](http://fukuchi.org/)
