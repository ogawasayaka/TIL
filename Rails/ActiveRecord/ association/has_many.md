# has_many 関連付け
- 他のモデルとの間に「1対多」のつながりがあることを示す。
- 「反対側」のモデルでは多くの場合belongs_toが使われる。
  
## has_many: dependent: :destroy について
dependent: :destroyの役割は、英語直訳の「依存して、削除する」のとおり、親モデルが削除された時に同時に紐づく子モデルも削除される。
>#結論
>dependent: :destroyを追加することで、
>「親モデルを削除する際に、その親モデルに紐づく「子モデル」も一緒に削除できる」ようになります。

>例えばユーザーが退会した場合、そのユーザーが投稿した記事も全て消えるように設定するのであれば、必須な知識です。
>引用元：　https://qiita.com/Tsh-43879562/items/fbc968453a7063776637

参考：　Railsガイド　https://railsguides.jp/v5.2/association_basics.html#has-many%E9%96%A2%E9%80%A3%E4%BB%98%E3%81%91
