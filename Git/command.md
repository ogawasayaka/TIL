- 初期設定を行う
```
$ git config --global user.name "XXXX"
$ git config --global user.email "XXXX@hogehoge.com"
```
- ローカルにリポジトリを作成し、リモートにプッシュする
```
$ git init
$ git add .
$ git commit -m "Initial commit"
$ git remote add origin https://github.com/XXXX/XXXXXX.git
$ git push -u origin master
```
- リモートからクローンする
```
$ git clone https://github.com/XXXX/XXXXXX.git
```
- リモートから変更を取得する
```
$ git pull
or
$ git fetch
$ git merge origin/master
```
- ファイルの登録（コミットするため）
```
$ git add <ファイル名>
```
- ファイルの変更や追加をコミット
```
$ git commit -m "コミットメッセージ"
```
ローカルの変更を確認する
```
$ git status
```
リモートとローカルのファイルの差分を抽出する
```
$ git diff <ファイル名>
```
commitの変更履歴をみる
```
$ git log
```
指定したcommitの変更点を見る
```
$ git show <コミットのハッシュ値>
```
リモートにプッシュ
```
$ git push origin <ブランチ名>
```
addの取り消し
```
$ git reset HEAD <ファイル名>
```
commitの取り消し
```
$ git reset --hard HEAD^
--hard：コミット取り消した上でワークディレクトリの内容も書き換えたい場合
--soft：ワークディレクトリの内容はそのままでコミットだけを取り消したい場合
HEAD^：直前のコミット
HEAD~{n} ：n個前のコミット
```
commitの打ち消し
```
$ git revert <コミットのハッシュ値>
```
コミットメッセージの修正
```
$ git commit --amend "新しいコミットメッセージ"
```
pushの取り消し
```
$ git reset --hard <戻したいコミットのハッシュ値>
$ git push -f
```
ローカルでブランチを作成
```
$ git branch <ブランチ名>
```
ローカルでブランチを切り替え
```
$ git checkout <ブランチ名>
```
ブランチ作成 & 切り替え
```
$ git checkout -b <ブランチ名>
```
ブランチ名の変更
```
$ git branch -m <古いブランチ名> <新しいブランチ名>
```
ブランチの削除
```
$ git branch -d <ブランチ名>
```
ローカルのブランチをリモートに反映
```
$ git push -u origin <ローカルのブランチ名>
```
リモートのブランチをローカル持ってくる
```
$ git branch <ブランチ名> origin/<ブランチ名>
```
リモートのブランチをローカル持ってくる & 切り替え
```
$ git checkout -b <ブランチ名> origin/<ブランチ名>
```
全てのブランチを確認する
```
$ git branch -a
```
ブランチを比較する
```
$ git diff <ブランチ名> <ブランチ名>
```
ブランチをマージする
```
$ git merge <ブランチ名>
fast-forwardの関係であっても必ずマージコミットを作る
$ git merge --no-ff <ブランチ名>
```
ブランチをリベースする
```
$ git rebase <ブランチ名>
※ mergeの場合は分岐元、rebaseの場合は分岐先のブランチで実行するという点に注意してください。
```
変更点を一旦退避させる
```
$ git stash save
```
退避した作業の一覧を見る
```
$ git stash list
```
退避した作業を戻す
```
$ git stash apply <stash名>
```
退避した作業を消す
```
$ git stash drop <stash名>
```
退避した作業をすべて消す
```
$ git stash clear
```
ファイル削除
```
$ git rm -f  <ファイル名>
```
ファイルリネーム
```
$ git mv <元のファイル名> <変えたいファイル名>
```
ファイルを最新のコミットの状態に戻す
```
$ git checkout HEAD <ファイル名>
```
ファイルを指定コミットまで戻す
```
$ git checkout <コミットのハッシュ値> <ファイル名>
```
.gitignore を無視して追加する
```
$ git add -f <ファイル名>
```
ディレクトリだけ登録(.gitkeepをディレクトリに作成する)
```
$ touch <ディレクトリ名>/.gitkeep
```
参考　https://qiita.com/kohga/items/dccf135b0af395f69144
