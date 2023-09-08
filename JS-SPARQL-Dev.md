# JavaScriptを用いたSPARQL処理の発展問題
## 演習課題2 
- 演習には「templete」フォルダにあるコードを利用すること 
- [演習課題1](https://github.com/oecu-kozaki-lab/JS-SPARQL-Exercise/blob/main/JS-SPARQL-Basic.md)で作成したコードを利用するので先に演習課題1を済ませておくこと 
- 最終的な2-5の動作イメージは[こちら](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex2-5.html)を参照 

### 2-1) SPARQLクエリの結果表示の汎用化 
[演習課題1-3,4](https://github.com/oecu-kozaki-lab/JS-SPARQL-Exercise/blob/main/JS-SPARQL-Basic.md#1-3-%E7%B5%90%E6%9E%9C%E3%81%AE%E3%83%AA%E3%83%B3%E3%82%AF%E5%87%A6%E7%90%86)で作成したプログラム（Ex1-4.html）における「?oの表示をURI/datatypeに応じて変える処理」をSPARQLクエリ`SELECT ?p ?o WHERE{wd:Q7105556 ?p ?o.} `で，得られた?pおよび?oの両方の表示に利用できるように修正したプログラムを作成しなさい．【Ex2-1.htmlとする】
- ヒント：演習課題1-3.4で作成した「?pや?oを表示するための処理」を関数として呼び出せるよう共通化すればよい
  
### 2-2) 入力したデータを用いたSPARQLクエリ生成例 
Ex2-1.htmlを改良して，「Webページに用意した入力欄で指定した任意のQID（wd:Qxxxxとする）」を主語とする述語(?p)，目的語(?o)を取得するSPARQLクエリ`SELECT ?p ?o WHERE{wd:Qxxxx ?p ?o.} `で，得られた結果を表示するプログラムを作成しなさい．【Ex2-2.htmlとする】
- ヒント：クエリ欄から得た「クエリのID部分」を「入力欄から得たQID」で置き換えてから検索を実行すればよい  
- ヒント：https://github.com/oecu-kozaki-lab/KGSearchForWD/blob/main/sample/template.html などを参考する

### 2-3) SPARQLクエリの結果表示の汎用化 
Ex2-2.htmlを改良して，任意のQID（wd:Qxxxxとする）の入力を`..../Ex2-3.html?id=Qxxxx`のようにURLのパラメータとして指定できるようにしたプログラムを作成しなさい．【Ex2-3.htmlとする】
‐ ヒント：URLのパラメータは`location.search`で取得できる[参考](https://www.javadrive.jp/javascript/webpage/index10.html)
- ヒント：https://github.com/oecu-kozaki-lab/KGSearchForWD/blob/main/sample/details.html , [情報工学実験の課題](https://drive.google.com/drive/u/0/folders/1XSfxHDPUPODmXQxbCXPLWyyTTWKQjguu)などを参考する

### 2-4) 任意のSPARQLクエリの結果表示処理【CSV出力】
Ex2-1.htmlを改良して，「任意のSPARQLクエリ」を入力し，結果を「カンマ区切り」で表示するプログラムを作成しなさい．【Ex2-4.htmlとする】
- ヒント：SPARQLクエリの結果として得られるデータの「変数一覧」は`keys`で配列として得られる，この配列を用いたfor文を考える．

### 2-5) 任意のSPARQLクエリの結果表示処理【HTML表】
Ex2-4.htmlを改良して，「任意のSPARQLクエリ」を入力し，結果を「HTMLの表」として表示するプログラムを作成しなさい．【Ex2-5.htmlとする】
- ヒント：HTMLのTABLEタグの利用については，Webサイトで入門ページを探すとよい（例えば，[こちら](https://webst8.com/blog/html-table/)）
- ヒント：KGSerach.jsの`function showResult(resultData,resultArea)`関数も参考には出来るが，「セルの結合」や「検索システム用の個別設定」が含まれているため，コードが複雑になっているので注意
  
