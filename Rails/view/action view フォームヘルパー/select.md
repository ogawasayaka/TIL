
# セレクトボックスを簡単に作成する

たとえば、ユーザーに選択して欲しい都市名のリストがあるとする。
selectヘルパーを使うと以下のようにセレクトボックスを作成できる。
```
<%= form.select :city, ["Berlin", "Chicago", "Madrid"] %>
```
上のコードで以下のHTMLが出力される。
```
<select name="city" id="city">
  <option value="Berlin">Berlin</option>
  <option value="Chicago">Chicago</option>
  <option value="Madrid">Madrid</option>
</select>
```
以下のようにセレクトボックスの表示名と別の<option>値を指定することも可能。
```
<%= form.select :city, [["Berlin", "BE"], ["Chicago", "CHI"], ["Madrid", "MD"]] %>
```
上のコードで以下のHTMLが出力される。
```
<select name="city" id="city">
  <option value="BE">Berlin</option>
  <option value="CHI">Chicago</option>
  <option value="MD">Madrid</option>
</select>
```
こうすることで、ユーザーには完全な都市名が表示されるが、params[:city]は"BE"、"CHI"、"MD"のいずれかの値になる。

最後に、:selected引数を使うとセレクトボックスのデフォルト値も指定できる。
```
<%= form.select :city, [["Berlin", "BE"], ["Chicago", "CHI"], ["Madrid", "MD"]], selected: "CHI" %>
```
上のコードで以下のHTMLが出力される。
```
<select name="city" id="city">
  <option value="BE">Berlin</option>
  <option value="CHI" selected="selected">Chicago</option>
  <option value="MD">Madrid</option>
</select>
```
参考　https://railsguides.jp/form_helpers.html#%E3%82%BB%E3%83%AC%E3%82%AF%E3%83%88%E3%83%9C%E3%83%83%E3%82%AF%E3%82%B9%E3%82%92%E7%B0%A1%E5%8D%98%E3%81%AB%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B
