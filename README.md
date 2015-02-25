# OverlayPlugin

## ビルド方法

※ リリースページでビルド済みのバイナリを配布していますので、面倒な方はそちらをお使いください。

手順:

* .NET Framework 4.5.1 をインストールします
* Microsoft Build Tools 2013 (http://www.microsoft.com/ja-jp/download/details.aspx?id=40760) をインストールします（Visual Studio 2013 がインストールされている場合は不要）
* ソースコード一式をチェックアウト、または ZIP ファイルでダウンロードして解凍します
* Thirdparty フォルダの中にある ACT フォルダに、ACT の実行ファイル（Advanced Combat Tracker.exe）をコピーします
* build.bat を実行します

うまくいけば、Build フォルダの中にプラグインが生成されます。

## 使用方法

OverlayPlugin.dll をプラグインとして ACT に追加します。
OverlayPlugin.dll 単体を抜き出しての使用はできません。他のフォルダに移したいときは、ほかの全てのファイルと一緒に移動させてください。

追加すると、「No data to show」、または DPS が表示されたウィンドウが表示されます。
非透過部分をドラッグすると移動でき、右下のハンドルをドラッグするとサイズの変更ができます。

ACT のプラグインタブにある「OverlayPlugin.dll」タブで、表示の切り替えやマウスクリックの透過、表示するファイルの設定などができます。

## トラブルシューティング

オーバーレイウィンドウなどが表示されない場合は、「Plugins」タブにある「OverlayPlugin.dll」タブ内の下部にあるログのメッセージをよく確認してください。

### `Error: AssemblyResolve: => System.NotSupportedException: ネットワーク上の場所から（以下略）` というログが表示される

インターネットからダウンロードしたZIPファイルをウィンドウズ標準のZIP展開機能を使用すると、信頼できないファイルとしてファイルにフラグが付与されることがあります。

このフラグがついている場合、他の信頼できない実行ファイルやDLLを読み込むことができず、上記のエラーが発生することがあります。

エクスプローラーでファイルを右クリックしてプロパティを選択し、下部にある「ブロックの解除」ボタンを押すことでこのフラグを解除することができますので、すべての DLL ファイルのフラグを解除してください。

また、ネットワークドライブを使用している場合にも、このエラーが出る可能性があります。ローカルドライブにファイルを移してから使用してください。

### `Error: AssemblyResolve: => System.IO.FileNotFoundException: 指定されたファイルが（以下略）` というログが表示される

プラグインがあるDLLと同じ場所に、必要なDLLが配置されていません。

使用方法にも書いているように、OverlayPlugin.dll 単体を別の場所にコピーして使用することはできません。移動させる場合は他のファイルと一緒に移動させてください。

### いつの間にか最前面じゃなくなっている

おそらくウィンドウズの仕様です。一度非表示にして再度表示させると直ります。

## カスタマイズ

プラグインが配置されているフォルダにある resources フォルダの中の、default.html を編集することでカスタマイズができます。 

JavaScript と HTML に関する基礎的な知識があれば編集できると思います。

## ライセンス

MIT ライセンスです。詳細は LICENSE.txt を参照してください。

## Other Languages:

* [English (EN)](../master/README-en.md)
