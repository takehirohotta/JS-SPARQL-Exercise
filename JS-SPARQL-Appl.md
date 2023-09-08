# JavaScriptの可視化ライブラリの利用
## 演習課題3 
- 演習には「templete」フォルダにあるコードを利用すること  
- 回答例は[「こちら」](https://oecu-kozaki-lab.github.io/JS-SPARQL-Exercise/Ex3-1.html)を参照 
### 3-1) d3.jsを用いた棒グラフの表示
https://wizardace.com/d3-barchart001/ のサンプルを参考にして，
```
SELECT ?item ?itemLabel ?h
WHERE{
  ?item wdt:P31 wd:Q1440300.
  ?item wdt:P17 wd:Q17.
  ?item wdt:P2048 ?h.
    SERVICE wikibase:label { bd:serviceParam wikibase:language "ja". }
}ORDER BY DESC(?h)
LIMIT 10
```
というSPARQLクエリで得られる結果を棒グラフに表示するプログラムを作成しなさい．  
- ヒント：まずはサンプルプログラムのソースコードをダウンロードして実行してみる．  
その上で，サンプルプログラムで「表示するデータ」を定義している部分を，SPARQLクエリで得た結果で作成するようにすればよい．
- ヒント２：SPARQLクエリの結果を用いてデータを作成するには、あらかじめ用意した配列`let datasete =[];`に，push関数でデータを追加していけばよい（[参考](https://www.javadrive.jp/javascript/array/index4.html)）．  
参考で示したサイトの例では「文字列」をpushしているが，`let val = { "name": "A", "value": 5 }`といった形で定義したデータをpushすることもできる．
  

### 3-2) d3.jsを用いた棒グラフの表示の練習
演習課題3-1のクエリを，「何かのランキングを検索する」別のクエリに差し替えたプログラムを作成しなさい．  
できれば，3-1で使用した以外の可視化ライブラリを探して利用するとよい（[参考](https://www.tohoho-web.com/ex/chartjs.html)）．
