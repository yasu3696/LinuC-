# findコマンド

<br>
<br>


## 🧠 基本構文

### find [検索開始ディレクトリ] [検索条件] [アクション]



## 🔎 よく使う検索条件

| 条件 | 意味 | 例 |
|--------|-----------|-----------|
| `-name "*.txt"` | 名前に `.txt` を含む | `find . -name "*.txt"` |
| `-type f` | 通常ファイル | `-type d` → ディレクトリ |
| `-size +1M` | サイズが 1MB より大きい | `-size -100k` は100KB未満 |
| atime | アクセス日を検索 |  |
| `-mtime -7` | 7日以内に更新 | `+30` なら30日より古い |
| `-user yasuda` | 所有者が `yasuda` |

<br>

## 🎯 よく使うアクション

| アクション | 説明 |
|----------------|---------------|
| `-print` | 検索結果を改行で区切って表示 |
| `-exec コマンド {} \;` | 条件に合った各ファイルにコマンド実行 |
| `｜ xargs コマンド` | 複数ファイルをまとめてコマンドに渡す（高速）|

<br>

## 🛠️ 実用例

| 📁 1. `.log` ファイルをすべて削除 |
|-----------------------------|
|find . -name "*.log" | xargs rm -f |



| 📜 2. `.txt` ファイルの内容を一覧表示 |
|----------------------------------|
| find . -name "*.txt" | xargs cat |



| 🗑️ 3. 空のディレクトリを探す |
|--------------------------|
| find . -type d -empty |



| 🔐 4. 実行権限のない `.sh` ファイルを見つける |
|----------------------------------------|
| find . -name "*.sh" ! -perm /u=x |



| 🧼 ファイル名にスペースがあるときの注意 |
|------------------------|
| find . -name "*.txt" -print0 | xargs -0 rm |

-   `-print0`: NULL区切りで出力
-   `-0`: `xargs` 側もNULL対応

→ 空白・改行を含むファイル名も安全に処理できます！
