# 新しいカラムを追加する
- マイグレーション名を"AddColumnToTable"にする。
- マイグレーション名の後ろにカラム名や型が続く形式にする。
- 適切なadd_column文を含むマイグレーションが作成されます。

例
```
$ bin/rails generate migration AddPartNumberToProducts part_number:string
```
上を実行すると以下のマイグレーションファイルが生成される。

```
class AddPartNumberToProducts < ActiveRecord::Migration[7.1]
  def change
    add_column :products, :part_number, :string
  end
end
```

## 新しいカラムにインデックスも追加したい場合
以下を実行すると、適切なadd_columnとadd_indexステートメントが生成される。
```
$ bin/rails generate migration AddPartNumberToProducts part_number:string:index
```
```
class AddPartNumberToProducts < ActiveRecord::Migration[7.1]
  def change
    add_column :products, :part_number, :string
    add_index :products, :part_number
  end
end
```
### ２個のカラムを追加する場合

以下を実行すると、productsテーブルに2個のカラムを追加するスキーママイグレーションを生成する。
```
$ bin/rails generate migration AddDetailsToProducts part_number:string price:decimal
```
```
class AddDetailsToProducts < ActiveRecord::Migration[7.1]
  def change
    add_column :products, :part_number, :string
    add_column :products, :price, :decimal
  end
end
```
参考　　Railsガイド　　https://railsguides.jp/active_record_migrations.html#%E6%96%B0%E3%81%97%E3%81%84%E3%82%AB%E3%83%A9%E3%83%A0%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B
