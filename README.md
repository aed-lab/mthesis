# 東京工科大学メディア学部 修士論文のテンプレート

# 使い方
Github Codespace・Vscode Devcontainer に対応しています。
DockerImageはPaperistというの軽量のイメージをベースに拡張してあります。
拡張項目は以下のとおり

| git              | Git操作  |
| sudo             | 学生Dev Container用 |
| openssh-client   | Git SSH接続  |
| ca-certificates  | HTTPS  |
| locales          | 日本語・英語locale  |
| GhostScript      | Ghostscript/ TeXでのeps処理 |
| python3          | thesis-monitor  |
| python3-yaml     | students.yml / snapshot処理 |
| poppler-utils    | pdfinfo（ページ数取得）  |

Github Codespacesで開くとそのまま作業して commitすることができます。

マスターファイルは main.tex です。こちらには基本的にソースファイルの inputのみを書きます。
本文が入ったLaTeXのソースファイルは srcの中に保存します。ファイル名を間違えないようにしましょう。

画像ファイルは fig の中に入れてください。GraphicsPathが通してあるのでそのまま参照できます。

論文リストは bib/ に置きます．サンプルは BibTeX.bib ですが変更してもかまいません。

VSCODE的にはDraw.ioインテグレーションが導入されますので、VSCODEの上で簡単な図なら書くことができます。


## 履歴
2024/10から Devcontainerに対応しているので、 Vscodeと docker がインストールされていれば環境は簡単に構築することができます。

2026/08から Github Codespacesに対応しているので、githubの上から
codespacesを開くことで、手元に何もインストールすることなくオンラインで編集、PDFの生成が可能です。
Codespacesは学生の無料プランの場合１ヶ月あたり180CPU時間、最低限のスペックが2コアなので 90時間使うことができます。
１ヶ月にそれ以上悩みたい場合や、オフラインでも作業したい場合には手元で vscode(+devcontainer) + WSL(3.0.3以降) の環境を整備してください。
WSLのアップデートに伴い、DockerDesktopは必要なくなりました。

2026/10から、Github Actions に対応しています。
commitして pushすると自動的にサーバ上でActionsが走って、PDFを作成します。
作成できたPDFは　Artifactとして保存されますので、週次での履歴を保存する意味でもこまめにCommitするとよいです。

