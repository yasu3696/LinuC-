# Debian形式のパッケージ管理
<br>
<br>
<br>

| <u>tree</u>|_|<u>1.7.05</u>|_|<u>amad64</u>|.|<u>red</u> |  
|--|--|--|--|--|--|--|
| &emsp;1 |  | &nbsp;&emsp;2 |  | &emsp;&emsp;3 |  | &nbsp;&nbsp;4 |

<br>

|  |  |
|--|--|
| 1 | パッケージの名前（ソフトウェアの名前） |
| 2 | パッケージ情報（と、ディビジョン番号） |
| 3 | CPUのアーキテクチャ（どのCPU向けのものか）|
| 4 | 拡張子（「.deb」はDeban系で利用するパッケージファイルであることを示す） |

<br>

-------

<br>

## dpkgコマンド

<br>

| dpkg | 基本構文 |
|--|--|
| 古くからDebian系で利用されているパッケージ管理システム | dpkg [オプション] **アクション** [パッケージ名など] |

| オプション | 説明 | 引数　パッケージ名など |
|--|--|--|
| -E | 同じバージョンがすでにインストールされていればインストールしない |  |
| -G | 新しいバージョンがすでにインストールされていればインストールしない |  |
| -R | ディレクトリ内を再帰的に処理する |
・多機能であるが、後出の管理システムに比べて頻雑
・パッケージのインストールや削除などは**root権限が必要**

<br>

### dpkgコマンドで使われる主なアクション一覧

|  |  |  |
|--|--|--|
| -i | パッケージファイル名 | パッケージをインストールする |
| -r（--remove） | パッケージ名 | 設定ファイルは残してパッケージを削除（アンインストール）する |
| -P（--purge） | パッケージ名 | 設定ファイルも含めてパッケージを完全にアンインストールする |
| -l（--list） | 検索パターン | インストール済みのパッケージを（検索して）表示する |
| -S | 検索パターン | 指定したファイルがどのパッケージからインストールされたのかを表示する |
| -C（--audit） |  | インストールが完了していない（不完全）パッケージの表示 |
| -L（--listfiles） | パッケージ名 | 指定したパッケージからインストールされたファイルを一覧で表示する |
| -s | パッケージ名 | 指定したパッケージの情報を表示する |
| --unpack | パッケージ名 | パッケージを展開する |
| --configure | パッケージ名 | 展開されたパッケージを構成（設定）する |
| -reconfigure | パッケージ名 | 指定したインストール済みのパッケージを再設定する |

<br>

## dpkgツールの設定ファイル

**/etc/dpkg/dpkg.cfg**
