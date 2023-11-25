## セットアップ
#### application.html.erb
```
<head>
  ...
  # application.jsの前に読み込めばロード前にgon変数にアクセスできる
  #
  # 以下のようなHTMLを生成してくれる
  # <script>
  # //<![CDATA[
  # window.gon={};gon.hoge=1;
  # //]]>
  # </script>
  <%= Gon::Base.render_data %>
  <%= javascript_include_tag "application" %>
  ...
</head>
```

## 使ってみる 
```
class ProductsController < ApplicationController
  def index
    # Rails側で変数をセット
    gon.hoge = 1

    ...
  end
end
```

#### ①コントローラ内において、以下のように,　　

gon.js内で使いたい変数名 = Rails内での変数　　

と書きます。　　
```
app/controllers/tasks_controller/rb

def edit
  @lavel_list = @task.lavels.pluck(:lavel_name).join(",")
  gon.lavel_list = @task.lavels.pluck(:lavel_name).join(",")
end
 
```
#### ②すると、javascriptの変数として、gon.lavel_listを使用することが出来ます。

```
app/assets/javascripts/task.js

$(document).on('turbolinks:load', function() {
  $("#task_lavels").tagit({
    fieldName:"tags[]"
  });
  if (gon.lavel_list) {
    tags = gon.lavel_list.split(",");
    for (i in tags){
       $('#task_lavels').tagit('createTag', tags[i])
     }
  }
})
``` 


参考　：https://nekorails.hatenablog.com/entry/2018/10/16/100750
    https://haayaaa.hatenablog.com/entry/2019/02/17/144329
