# active_decorator

## active_decoratorとは？　　
デコレーターとはビューデザインの一つ。
複雑なビューを表現するときに、新しいレイヤーのdecorator層を新しく定義することによって、モデルとビューを橋渡ししている。

## Decoratorのいいところ
>Modelに対応したViewへのロジックをModelと切り離して書けていい感じですよね。
>このDecoratorのいいところは、

>1.Modelに書かずにModelに対応したViewへの表示フォーマットを用意出来ること  
>2.Decoratorの中にActionViewのhelperを使用することが出来ること  

>だと思っています。
>1のほうはいいとして、2のほうはactive_recordで登場する例を用いると以下での link_toのようなhelperをDecoratorの中に直接書けるということです。  
`app/decorators/user_decorator.rb`  
```
    module UserDecorator  
      def full_name  
        "#{first_name} #{last_name}"  
      end  
      def link  
        link_to full_name, website  
      end
    end
```
>`app/views/users/index.html.erb`
```
    <% @users.each do |user| %>
      <%= user.link %><br>
    <% end %>
```
>引用元　　https://qiita.com/shizuma/items/ce9e863e9c94e88e0a57#decorator%E3%81%AE%E5%88%A9%E7%82%B9

## 導入
- gemのインストール
```
gem 'active_decorator'
```
```
$ bundle install
```
- ex) Userモデルのdecoratorの作成

```
$ bin/rails g decorator user
```
新しく`app/decorators`というディレクトリが作られ、`user_decorator.rb`が作成される。

## helperとdecorator
>まずはモデルにメソッドを定義することを検討する  
>ただ、肥大化して可読性が落ちそうな場合は、helperやdecoratorに切り分けることを検討する  
> - モデルに依存しないときはhelper  
> - モデルに依存するときはdecorator  

>引用元 https://qiita.com/YokoYokoko/items/b994e598c98e39ba0d58#%E3%81%BE%E3%81%A8%E3%82%81

- 参考  
パーフェクトRuby on Rails すがわら まさのり (著), 前島 真一 (著), 近藤 宇智朗 (著), 橋立 友宏 (著)  
[公式]: https://github.com/amatsuda/active_decorator
　
