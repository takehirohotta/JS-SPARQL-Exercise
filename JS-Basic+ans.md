# JavaScriptの基礎【解答付き】
## 演習課題0 
- 演習には「templete」フォルダにあるコードを利用すること  
- JavaScriptの基本的な使い方は，[MDNのチュートリアル](https://developer.mozilla.org/ja/docs/Learn/Getting_started_with_the_web/JavaScript_basics)，[JavaDriveのJavaScript入門](https://www.javadrive.jp/javascript/)などを参照する

### 0-1) JavaScriptの基本テンプレートの動作確認 【[解答例](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex0-1.html)】
Ex0-1.htmlを実行し，ボタンを押すとダイアログに「Hello World!」と表示するプログラムの動作の仕組みを確認しなさい．

### 0-2) テキスト入力の処理 【[解答例](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex0-2.html)】
Ex0-1.htmlを修正して，ボタンを押すとダイアログに「テキスト入力欄（複数行入力可能）に入力したテキスト」を表示するプログラムを作りなさい．

### 0-3) テキストのWebページへの表示処理 【[解答例](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex0-3.html)】
Ex0-2.htmlを修正して，ボタンを押すと，開いているWebページの下部（ソースでは`<div id="result_div"></div>`で示された部分）に「テキスト入力欄（複数行入力可能）に入力したテキスト」を表示するプログラムを作りなさい．  
- 複数行入力した際も，正しく改行されるように注意すること
- ボタンを押すたびに，入力内容が「追記する形」で表示される方法も試す

### 0-4) テキスト入力の処理 【[解答例](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex0-4.html)】
Ex0-3.htmlを修正して，１行分のテキストを入力する「キーワード入力欄」を追加なさい．  
その上で，ボタンを押すと，開いているWebページの下部に表示される「テキスト入力欄（複数行入力可能）に入力したテキスト」中で，「キーワード入力欄」に入力したキーワードが「強調表示」されるプログラムを作りなさい．  
- 強調表示の仕方は，「太字にする」，「背景の色を変える」など，いくつか試すこと
- 複数のキーワードを「半角スペース区切り」で入力し，それぞれのキーワードに一致する箇所を強調表示できるような拡張も行う
