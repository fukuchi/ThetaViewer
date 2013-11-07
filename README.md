Theta Viewer
============

RICOH THETAのような正距円筒図法(Equirectangular Projection)のパノラマ画像をWebでブラウズできるビューアーです。
[jQuery](http://jquery.com/)のプラグインになっています。
描画にはJavaScriptによる3Dライブラリ[three.js](http://threejs.org/)を使用しています。

Documentation
-------------
1. jQueryとthree.jsをHTMLに先に読み込みます。以下の例は、jQueryとthree.jsをダウンロードし、jsフォルダに置いた場合のものになっています。
2. Theta ViewerをHTMLに読み込みます。
3. body要素の中にTheta Viewerでパノラマ画像を表示する要素(例では#theta-viewer)を用意します。
4. パノラマ画像を表示するコードを記述する。具体的には「jQuery(パノラマ画像を表示したいセレクタ).createThetaViewer(画像ファイル);」で表示できます。以下の例では、#theta-viewerにimgフォルダの中のtheta.jpgを表示しています。

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <script src="js/jquery-1.10.2.min.js"></script>
  <script src="js/jquery-migrate-1.2.1.min.js"></script>
  <script src="js/three.min.js"></script>
  <link rel="stylesheet" href="css/styles.css">
  <script src="js/theta-viewer.js"></script>
  <title>Sample of THETA Viewer</title>
</head>
<body>
  <div id="theta-viewer"></div>
  <script>
/*global jQuery */
(function ($) {
    'use strict';
    // #theta-viewerにパノラマ画像img/theta.jpgを表示
    $("#theta-viewer").createThetaViewer('img/theta.jpg');
}(jQuery));
  </script>
</body>
</html>
```

Platform
--------

- Firefox
- Chrome
- Safari

License
-------

MIT License

Author
------

[小久保温(Atsushi Kokubo)](http://www.dma.aoba.sendai.jp/~acchan/).