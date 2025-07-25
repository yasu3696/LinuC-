# tarコマンド

<br>
<br>

## 📦 tarの基本構文

### tar [オプション] [アーカイブファイル名] [対象ファイルやディレクトリ]

<br>


## 🔧 よく使うオプションの例

| オプション | 説明 |
|---|---|
| `-c` | 新しいアーカイブを作成（create）|
| `-x` | アーカイブを展開（extract）|
| `-t` | アーカイブの内容を一覧表示 |
| `-f` | ファイル名の指定（file）|
| `-v` | 処理中のファイル名を表示（verbose）|
| `-z` | gzip圧縮／解凍を行う（.tar.gzなどに対応）|
| `-j` | bzip2圧縮を使う（.tar.bz2用）|
| `-J` | xz圧縮／解凍を行う（.tar.xz にしたいとき使う）|

<br>


## 📎 補足：圧縮形式によるオプションの違い
| 拡張子 | 圧縮形式 | オプション |
|---|---|---|
| .tar | なし | -cvf | 
| .tar.gz | gzip | -czvf | 
| .tar.bz2 | bzip2 | -cjvf | 
| .tar.xz | xz | -cJvf | 

<br>

-------------------------------------------------------------------------------

## 💡 使用例

| ファイルを.tar.gzにまとめる | 説明 |
|-----------|--------|
| tar `-czvf` archive.tar.gz ./myfolder | `myfolder` ディレクトリを `archive.tar.gz` に圧縮 |

<br>

| アーカイブを展開する | 説明 |
|---------|------------|
| tar `-xzvf` archive.tar.gz | `archive.tar.gz` を現在のディレクトリに解凍 |

<br>

| .tarファイルを展開する（圧縮なし）| 
|--------------|
| tar -xvf archive.tar | 

<br>

🧠 ワンポイント豆知識

`.tar` ファイルは単なる「まとめファイル」であって、圧縮はされていません。そこに `-z` や `-j` を加えることで、gzip や bzip2 による圧縮がかかるんですね！
