# upto 繰り返し処理
upto メソッドは指定した開始数から最大数まで 1 つずつ増加しながら繰り返しを行いたいときに使用。
```
オブジェクト.upto(max){|変数|
  実行する処理1
  実行する処理2
}
```
または
```
オブジェクト.upto(max) do |変数|
  実行する処理1
  実行する処理2
end
```
- オブジェクトに指定した数値が max よりも大きい場合は繰り返し処理は行われない。
- upto メソッドは、変数に「オブジェクト」から max までの数値を順に代入しながら { から } までの処理(又は do から end までの処理)を実行する。
- 1回繰り返す毎に1ずつ数値は増加。(「|変数|」の部分は省略可)。

具体的には
```
3.upto(7){|num|
  puts("num = " + num.to_s)
}
```
- 上記の場合は変数「num」に数値の 3 から 7 まで順に代入しながら { から } までの処理を繰り返す。

# downto　繰り返し処理
downto メソッドは指定した開始数から最小数まで1つずつ減らしながら繰り返す。
```
オブジェクト.downto(min){|変数|
  実行する処理1
  実行する処理2
}
```
または
```
オブジェクト.downto(min) do |変数|
  実行する処理1
  実行する処理2
end
```
- オブジェクトに指定した数値が min よりも小さい場合は繰り返し処理は行われない。
- downto メソッドは、変数に「オブジェクト」から min までの数値を順に代入しながら { から } までの処理(又は do から end までの処理)を実行。
- 1回繰り返す毎に1ずつ数値は減る。(「|変数|」の部分は省略可)。

具体的には
```
7.downto(3){|num|
  puts("num = " + num.to_s)
}
```
- 上記の場合は変数「num」に数値「7」から「3」まで順に代入しながら「{」から「}」までの処理を繰り返す。

参考　https://www.javadrive.jp/ruby/for/index6.html#section1
