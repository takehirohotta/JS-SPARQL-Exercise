# JavaScriptを用いたSPARQL処理の基礎
## 演習課題1 
- 演習には[「templete」](https://github.com/oecu-kozaki-lab/JS-SPARQL-Exercise/tree/main/templete)フォルダにあるコードを利用すること（ZIP圧縮したものは[こちら](https://github.com/oecu-kozaki-lab/JS-SPARQL-Exercise/blob/main/templete.zip)からダウンロード可)  
- 最終的な1-4の結果の動作イメージは[こちら](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex1-4.html)
 
### 1-1) SPARQLクエリ実行の基本テンプレートの動作確認 
Ex1-1.htmlを実行し，WikidataのSPARQLエンドポイントで`SELECT ?o WHERE{wd:Q7105556 wdt:P131 ?o.} `というSPARQLクエリを実行して，得られた?oの値を表示するプログラムの動作の仕組みを確認しなさい．  
具体的には，以下の内容を確認する．
- SPARQLクエリを実行している処理（関数やその引数の設定※関数の中身は参考程度に見ればよい）
- SPARQLクエリを実行した結果のJSON形式のデータ（実行時に「クエリ実行結果の戻り値(JSON形式）
」に表示される内容）
- SPARQLクエリを実行した結果をHTMLとして表示する処理（関数の処理の中身も確認する）
  
### 1-2) 結果が複数行となるSPARQLの処理
Ex1-1.htmlで実行するSPARQLクエリを`SELECT ?p ?o WHERE{wd:Q7105556 ?p ?o.} `に変更し，?pと?oの組を表示するプログラムを作成しなさい，【Ex1-2.htmlとする】
- ?pと?oの組は1行で表示し，間に「---」など区切りが分かるような記号を挿入すること
- ヒント：検索結果のデータの長さは`data.length`で得られるので，これを用いてfor文を使えばよい
- ヒント：HTMLでの改行には`<BR>`タグを用いる

### 1-3) 結果のリンク処理
Ex1-2.htmlを修正し，クエリ結果として得られた「?oの値」が「URI」のとき，結果表示を「該当URIへのハイパーリンクとする」プログラムを作成しなさい．【Ex1-3.htmlとする】
- 値がURIかどうかは，`data[i]['o'].type`で判定できる
  - クエリの実行結果のJSONデータ（サンプルプログラムを実行したら表示される）との対応を確認しながら処理を考えるとよい．  
- HTMLでのハイパーリンク表示には`<a href="リンク先URL" target="_blank">`のタグを使うとよい．（`target="_blank">`は表示先のウィンドウの指示だが，省略も可能）

### 1-4) 結果のラベル処理
Ex1-3.htmlを修正し，クエリ結果として得られた「?oの値」が「リテラル（文字列）」のとき，「言語（xml:lang）」や「データタイプ（datatype）」の情報も結果に表示プログラムを作成しなさい．【Ex1-4.htmlとする】
- 「言語（xml:lang）」は`大阪電気通信大学@ja`のように「値」の末尾に「@言語コード」を付与して表す
- ヒント：「言語（xml:lang）」の取得は`data[i]['o'].xml:lang`ではなく`data[i]['o']['xml:lang']`のように記載する必要があるので注意
- 「データタイプ（datatype）」は`2022-09-24T16:46:19Z^^http://www.w3.org/2001/XMLSchema#dateTime`のように「値」の末尾に「^^データタイプのURI」を付与して表す

