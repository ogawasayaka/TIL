## リソースベースのルーティング (以下リソースルーティング) 

- resourcesを宣言するだけで、コントローラのindex、show、new、edit、create、update、destroyアクションを1行で宣言が完了する。

## Web上のリソース
- ブラウザはRailsに対してリクエストを送信する際に、特定のHTTPメソッド（GET、POST、PATCH、PUT、DELETEなど）を使って、URLに対するリクエストを作成する。
- 上に述べたHTTPメソッドは、いずれもリソースに対して特定の操作の実行を指示するリクエスト。
- リソースルーティングでは、関連するさまざまなリクエストを1つのコントローラ内のアクションに割り当てる。

Railsアプリケーションが以下のHTTPリクエストを受け取る。
```
DELETE /photos/17
```
- このリクエストは、特定のコントローラ内アクションにマッピングさせるようルーターに要求している。最初にマッチしたのが以下のルーティングだとする。
```
resources :photos
```
- Railsはこのリクエストをphotosコントローラ内のdestroyアクションに割り当て、paramsハッシュに{ id: '17' }を含める。


### CRUD、verb、アクション
- Railsのリソースフルルーティングでは、（GET、PUTなどの）各種HTTP verb（動詞、HTTPメソッドとも呼ぶ） と、コントローラ内アクションを指すURLが対応付1つのアクションは、データベース上での特定のCRUD（Create/Read/Update/Delete）操作に対応付けられるルールになっている。

たとえば、以下のようなルーティングが1つあるとする。
```
resources :photos
```
上の記述により、アプリケーション内に以下の7つのルーティングが作成され、いずれもPhotosコントローラに対応付けられる。
```
HTTP verb	パス	コントローラ#アクション	目的
GET	/photos	photos#index	すべての写真の一覧を表示
GET	/photos/new	photos#new	写真を1つ作成するためのHTMLフォームを返す
POST	/photos	photos#create	写真を1つ作成する
GET	/photos/:id	photos#show	特定の写真を表示する
GET	/photos/:id/edit	photos#edit	写真編集用のHTMLフォームを1つ返す
PATCH/PUT	/photos/:id	photos#update	特定の写真を更新する
DELETE	/photos/:id	photos#destroy	特定の写真を削除する
```
Railsのルーターでは、サーバーへのリクエストをマッチさせる際にHTTP verbとURLを使っているため、  
4種類のURL（/photos、/photos/new、/photos/:id、/photos/:id/edit）が7種類の異なるアクション（index、show、new、create、edit、update、destroy）に割り当てられる。

Railsのルーティングは、ルーティングファイルの「上からの記載順に」マッチする。
このため、たとえばresources :photosというルーティングがget 'photos/poll'よりも上の行にあれば、resources行のshowアクションがget行の記述よりも優先されるので、
get行のルーティングは有効にならない。これを修正するには、get行をresources行 よりも上 の行に移動する。これにより、get行がマッチするようになる。

参照　https://railsguides.jp/routing.html#web%E4%B8%8A%E3%81%AE%E3%83%AA%E3%82%BD%E3%83%BC%E3%82%B9
