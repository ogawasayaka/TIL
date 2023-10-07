# draper
- decoratorの作成　　
- 表示に関する処理を切り出して、モデルの肥大化を防ぐ。
## 導入
- gem のインストール
```
  gem 'draper'
```
```
  $ bundle install
```
- セットアップ
```
# app/decorators/application_decorator.rb を作成
# ApplicationDecoratorは全てのDecoratorの親クラスになる
$ rails generate draper:install
```
## ActiveDecoratorとの違い


### ActiveDecorator
ActiveDecoratorは、decorateモデルを作成せずにメソッドを使うことができる。
>draperと違って、特にdecorateモデルをつけなくてもデコレーターメソッドを使える。
>というのも、初期化時にActiveModelやActionControllerに対してdecorateメソッドを実行しきっているから
>引用元　　https://qiita.com/Coolucky/items/150875b8f5d7a50c7d79

公式：　https://github.com/drapergem/draper　　
参考：　https://qiita.com/Coolucky/items/150875b8f5d7a50c7d79  
     https://qiita.com/mmaumtjgj/items/50c8ac82ca5583cac254
