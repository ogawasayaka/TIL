# 組み込み変数ARGV(argument vector)
- argumentは引数のことで、ARGVはプログラムを実行した際に指定された引数を格納する配列。
- rubyコマンドとプログラムファイル名が除かれているので、純粋な引数のみが格納される。
```
# sample.rb
arg = ARGV[0].to_i
```
```
$ sample.rb 9
```
- sample.rbファイルをターミナルで実行。その際、引数として適当な数字を渡す
- 渡される引数はstring型になっているので、もし数値そして使いたいのであればto_iメソッドで変換する

参考　https://okmt-aya-26.hatenablog.com/entry/2022/05/16/133544
