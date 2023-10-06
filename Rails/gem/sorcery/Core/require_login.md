# require_login
ログインしていないユーザーをアクション単位で弾く。  
アクセスしようとしたURLをセッションに格納し、`not_authenticated`を実行するメソッド。  
以下のようにコントローラーないで`before_action`で指定する。
```
before_action :require_login
```

アクションごとに変える場合は、`only: :action`をつける。 
アクション内の分岐など、もっと細かい部分で弾きたい場合は、`logined_in?`を使う。 
____
https://github.com/Sorcery/sorcery　　　
https://qiita.com/aiandrox/items/65317517954d8d44d957
