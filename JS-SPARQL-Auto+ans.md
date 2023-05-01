# JavaScriptを用いたSPARQL処理の自動化【解答例】
## 演習課題4 
- 演習には「templete」フォルダにあるコードを利用すること 
- 回答例は「sample」フォルダを参照 
### 4-1) SPARQLクエリの結果表示の汎用化 【[解答例](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex4-1.html)】
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
  
### 4-2) SPARQLクエリの結果表示の汎用化 【[解答例](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex4-2.html)】
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
  　
