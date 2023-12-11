## csvクラス

### 読み込み

```
require "csv"

csv_text = <<~CSV_TEXT
  Ruby,1995
  Rust,2010
CSV_TEXT

IO.write "sample.csv", csv_text

# ファイルから一行ずつ
CSV.foreach("sample.csv") do |row|
  p row
end
# => ["Ruby", "1995"]
#    ["Rust", "2010"]

# ファイルから一度に
p CSV.read("sample.csv")
# => [["Ruby", "1995"], ["Rust", "2010"]]

# 文字列から一行ずつ
CSV.parse(csv_text) do |row|
  p row
end
# => ["Ruby", "1995"]
#    ["Rust", "2010"]

# 文字列から一度に
p CSV.parse(csv_text)
# => [["Ruby", "1995"], ["Rust", "2010"]]
```

### 書き込み
```
require 'csv'

# ファイルへ書き込み
CSV.open("path/to/file.csv", "wb") do |csv|
  csv << ["row", "of", "CSV", "data"]
  csv << ["another", "row"]
  # ...
end

# 文字列へ書き込み
csv_string = CSV.generate do |csv|
  csv << ["row", "of", "CSV", "data"]
  csv << ["another", "row"]
  # ...
end
```
https://docs.ruby-lang.org/ja/latest/library/csv.html
