
Use the reviews_sort request parameter to control sorting.
https://developers.google.com/maps/documentation/places/web-service/search-find-place?hl=ja#Place-reviews


### Find Place from Query
- Find Place from Query の場合は、テキスト入力を受け取り、場所を返します。お店やサービスの名前や住所など、場所に関するあらゆる入力内容を受け取ります。  
- Find Place from Query リクエストを実行するには、PlacesService の findPlaceFromQuery() メソッドを呼び出します。このメソッドは次のパラメータを受け取ります。

- query（必須）: 検索するテキスト文字列（「レストラン」、「123 番通り」など）です。地名、住所、施設のカテゴリのいずれかを入力する必要があります。他の種類のテキストを入力した場合、有効な結果が返されず、エラーが発生する場合があります。Places API はこの文字列と一致する候補を、関連性の高い順に並べて結果として返します。
- fields（必須）: 返す場所データのタイプを指定する 1 つ以上のフィールド。
- locationBias（省略可）: 検索領域を定義する座標。値は次のいずれかになります。
- LatLngLiteral または LatLng オブジェクトとして指定された緯度 / 経度座標のセット
矩形の境界（2 つの緯度 / 経度のペア、または LatLngBounds オブジェクト）
緯度 / 経度を中心とする半径（メートル単位）
結果オブジェクトと google.maps.places.PlacesServiceStatus レスポンスを処理するため、findPlaceFromQuery() にコールバック メソッドを渡す必要もあります。

