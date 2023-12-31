# ActiveRecordについて
- ActiveRecordとは、MVCで言うところのMに相当するシステム階層。
- ORM（オブジェクトリレーションマッピング）システムに記述されている「Active Recordパターン」を実装したもの。
## ActiveRecoredパターン
- データベースアクセスのロジックを常にオブジェクトに含めておくことで、そのオブジェクトの利用者にデータベースへの読み書き方法を指示できると言う立場をとる。
## O/Rマッピング
- オブジェクト/リレーショナル（O/RマッピングやORMと略）とは、アプリケーションが持つリッチなオブジェクトをRDBMSのテーブルに接続すること。
- SQL文を書く代わりにアクセスコードを書くだけでオブジェクトの属性やリレーションシップをDBに保存したり、読み出しが可能となる。
## ORMフレームワークとしてのActiveRecord
- モデル及びモデル内のデータを表現する
- モデル同士のアソシエーションを表現する
- 関連づけられているモデル間の継承階層を表現する
- データをデータベースで永続化する前にバリテーションを行う
- データベースをオブジェクト指向スタイルで操作する

____
参考：　[Railsガイド]https://railsguides.jp/active_record_basics.html#crud-%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%AA%AD%E3%81%BF%E6%9B%B8%E3%81%8D
