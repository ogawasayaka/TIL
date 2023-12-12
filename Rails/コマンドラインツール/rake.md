## カスタムRakeタスク

- 独自のRakeタスクの拡張子は.rakeで、 Rails.root/lib/tasks配下に保存します。
- 独自のタスクを作成できる bin/rails generate taskというコマンドもあります。

```
desc "手短でクールなタスクの概要"
task task_name: [:prerequisite_task, :another_task_we_depend_on] do
  # マジックをここに書く
  # 有効なRubyコードなら何でも書ける
end
```
https://railsguides.jp/command_line.html#%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0rake%E3%82%BF%E3%82%B9%E3%82%AF
