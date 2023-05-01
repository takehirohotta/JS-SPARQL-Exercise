# JavaScriptの可視化ライブラリの利用【解答付き】
## 演習課題3 
- 演習には「templete」フォルダにあるコードを利用すること  
- 回答例は「sample」フォルダを参照 
### 3-1) d3.jsを用いた棒グラフの表示【仮】【[解答例](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex3-1.html)】
https://wizardace.com/d3-barchart001/ のサンプルを参考にして，
```
SELECT ?item ?itemLabel ?h
WHERE{
  ?item wdt:P31 wd:Q1440300.
  ?item wdt:P17 wd:Q17.
  ?item wdt:P2048 ?h.
    SERVICE wikibase:label { bd:serviceParam wikibase:language "ja". }
}
```
というSPARQLクエリで得られる結果を棒グラフに表示するプログラムを作成しなさい．

### 3-2) d3.jsを用いた棒グラフの表示の練習
演習課題3-1のクエリを，「何かのランキングを検索する」別のクエリに差し替えたプログラムを作成しなさい．
