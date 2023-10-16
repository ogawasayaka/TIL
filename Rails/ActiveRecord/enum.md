# enum 
- enumを使うと、属性で使う値を配列で定義して名前で参照できるようになる。
- enumがデータベースに実際に保存されるときは、値に対応する整数値が保存される。

## enumの宣言

- enumを宣言すると、enumのすべての値について以下が作成される。
- enum値のいずれかの値を持つ（またはもたない）すべてのオブジェクトの検索に利用可能なスコープが作成される
- あるオブジェクトがenumの特定の値を持つかどうかを判定できるインスタンスメソッドを作成する
- あるオブジェクトのenum値を変更するインスタンスメソッドを作成する
たとえば
```
class Order < ApplicationRecord
  enum :status, [:shipped, :being_packaged, :complete, :cancelled]
end
```
このときstatus enumのスコープが自動的に作成され、以下のようにstatusの特定の値を持つ（または持たない）すべてのオブジェクトを検索できるようになる。
```
irb> Order.shipped
=> #<ActiveRecord::Relation> # all orders with status == :shipped
irb> Order.not_shipped
=> #<ActiveRecord::Relation> # all orders with status != :shipped
```
以下の?付きインスタンスメソッドは自動で作成される。以下のようにモデルがstatus enumの値を持っているかどうかをtrue/falseで返す。
```
irb> order = Order.shipped.first
irb> order.shipped?
=> true
irb> order.complete?
=> false
```
以下の!付きインスタンスメソッドは自動で作成される。最初にstatusの値を更新し、次にstatusがその値に設定されたかどうかをtrue/falseで返す。
```
irb> order = Order.first
irb> order.shipped!
UPDATE "orders" SET "status" = ?, "updated_at" = ? WHERE "orders"."id" = ?  [["status", 0], ["updated_at", "2019-01-24 07:13:08.524320"], ["id", 1]]
=> true
```
参考　https://railsguides.jp/active_record_querying.html#enum

