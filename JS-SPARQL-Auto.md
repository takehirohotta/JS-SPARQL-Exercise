# JavaScriptを用いたSPARQL処理の自動化
## 演習課題4 
- 演習には「templete」フォルダにあるコードを利用すること 
- 回答例は「[こちら](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex4-1.html)」を参照 
### 4-1) 入力したデータ（単語のリスト）に応じたSPARQLクエリの作成+自動実行 
演習課題2-4で作成したプログラム（Ex2-4.html）を利用してSPARQLクエリ
```
SELECT ?s ?sLabel 
WHERE{
?s ?p "#INPUT#"@ja.
SERVICE wikibase:label { bd:serviceParam wikibase:language "ja". }
}     
```
の`#INPUT#`を，
```
大阪府
京都府
兵庫県 
```
のような1行ごとに１単語を記入したテキストに置き換えて，連続で実行するプログラムを作成しなさい．【Ex4-1.htmlとする】  
- ヒント：入力したデータ（単語のリスト）を「単語ごとに分割」するには，<b>split関数</b>を使うとよい([参考](https://www.javadrive.jp/javascript/string/index1.html))  
→「改行コード（\n）」を区切りとして分割すればよい．
- ヒント：SPARQLクエリを「リストにある単語の数」だけ繰り返す．結果を表示する際に，前までのクエリの結果に「追記する」必要があるので注意．
  
### 4-2) 入力したCSVデータに応じたSPARQLクエリの作成+自動実行 
演習課題4-1で作成したプログラム（Ex4-1.html）を改良してSPARQLクエリ
```
select DISTINCT ?s ?sLabel ?o ?oLabel
{ 
    ?s rdfs:label|skos:altLabel "#INPUT#"@ja. 
    ?s ?p ?o.
    ?prop wikibase:directClaim  ?p . 
    ?prop rdfs:label|skos:altLabel "#PROP#"@ja.

SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],ja,en". }
}      
```
の`#INPUT#`と`#PROP#`を，
```
君の名は。,監督
ドラゴンボール,登場人物
天気の子,声優
大阪電気通信大学,所在地
寝屋川市,人口 
```
のような1行ごとにカンマ区切りで記入したテキストに置き換えて，連続で実行するプログラムを作成しなさい．【Ex4-2.htmlとする】  
- ヒント：split関数による分割を，複数回，組み合わせて用いる． 
  　
