これから「プライベートリポジトリ」というリモートリポジトリを作成します。
プライベートリポジトリは、**あなただけ**がアクセスできるリモートリポジトリです。\
外部の誰かに見られることはありません。安心して使ってください。
特に決まっていない？　では、試しに議事録を置いてみてはどうでしょうか。議事録を回覧すると「そういう意図じゃない」ということで元の内容から変更がかかることがあります。誰の意図で変更がかかったのかも含めて残しておくと、責任の所在を明確にできます。
![GitHubTop](img/Cap1_2-1_GitHubTop.png)

  「クローンして使うならここにチェック入れてね」と書いてあります。**今回は必ずチェックを入れてください**。
上図のリポジトリは、片倉だけがアクセスできるリポジトリです。\
試しに\
[https://github.com/ktkraoichi/FaultofTheDreakEquation](https://github.com/ktkraoichi/FaultofTheDreakEquation)\
へアクセスしてみてください。
![404NotFound](img/Cap1_2-30_404NotFound.png)
「お探しのページは見つかりませんでした」と言われます。\
あなたのプライベートリポジトリも、あなただけがアクセスできます。他の人からは見えません。

それではあなたのプライベートリポジトリをローカルリポジトリにクローンしましょう。\
ブラウザはそのままにしておいてくださいね。

Sourcetree で操作する人はそのまま進んでください。
### 3.1. Sourcetree で操作する人

Sourcetree を起動してください。

新しいタブを作成します。\
緑色のボタン、 **Clone or download** をクリックすると、プライベートリポジトリのURLが表示されます。\
「元のパス/URL:」の欄に、コピーしたプライベートリポジトリの URL を貼りつけます。

**Initial commit** （最初のコミット）があることを確認できましたか？

README.md の内容を、画面右下の「ファイルの内容」で確認してください。\
"#" 以降のテキストはリポジトリの名前と一致していますか？\
2行目のテキストはリポジトリの Description と一致していますか？
**Initial commit** は、あなたがリモートリポジトリを作成したとき、自動的に生成されたセーブデータです。 README.md だけが存在します。\
リモートリポジトリにあった **Initial commit** というセーブデータがローカルリポジトリにも存在し、リモートリポジトリに登録した内容が README.md に書かれていた。\
これは無事にリモートリポジトリからローカルリポジトリにクローンできた、ということです。

ディスクが壊れてしまったり、お使いのパソコンが爆発したりしても、リモートリポジトリが残っていれば大丈夫。もういちどクローンすれば元通りになります。
緑色のボタン、 **Clone or download** をクリックすると、プライベートリポジトリのURLが表示されます。\
例： `git clone https://github.com/ktkraoichi/FaultofTheDreakEquation.git`\
※この例をコピペしてもエラーになりますよ
$ git clone https://github.com/ktkraoichi/FaultofTheDreakEquation.git
Cloning into 'FaultofTheDreakEquation'...
`git show` というコマンドで、最新のコミットに関する詳細を確認できます。

$ git show
commit 485950ec21fbce48f3dd210c94da5c2a58cc29e4 (HEAD -> master)
Author: ktkraoichi <ktkrao1@gmail.com>
Date:   Mon Feb 17 12:49:18 2020 +0900

    Initial commit <- コミットメッセージ

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..dbc45d6
--- /dev/null
+++ b/README.md
@@ -0,0 +1,2 @@
+# FaultofTheDreakEquation <- リポジトリの名前
+Nが2になった日の原稿管理リポジトリ <- Description
```
Date の次、空行に挟まれている行にご注目。\
これはコミットメッセージです。\
コミットメッセージは **Initial commit** になっていますか？
表示された詳細のうち、最後の二行にもご注目。\
今回は「README.md」に書かれたテキストが表示されます。\
"#" 以降のテキストはリポジトリの名前と一致していますか？\
2行目のテキストはリポジトリの Description と一致していますか？

無事にクローンできたなら、素晴らしい！\
これでリモートリポジトリとローカルリポジトリを繋ぐことができました。

**Initial commit** は、あなたがリモートリポジトリを作成したとき、自動的に生成されたセーブデータです。 README.md だけが存在します。\
リモートリポジトリにあった **Initial commit** というセーブデータがローカルリポジトリにも存在し、リモートリポジトリに登録した内容が README.md に書かれていた。\
これは無事にリモートリポジトリからローカルリポジトリにクローンできた、ということです。

前回、リモートリポジトリは「ローカルのデータを転送し、複数人で共有できる場所」と説明しました。\
一人で運用する場合、リモートリポジトリは「オンライン上にローカルのバックアップを作成する場所」と考えてください。\
ディスクが壊れてしまったり、お使いのパソコンが爆発したりしても、リモートリポジトリが残っていれば大丈夫。もういちどクローンすれば元通りになります。

それでは次に進みましょう！

## 4. ローカルリポジトリにコミットを積み上げる

リモートリポジトリとローカルリポジトリの準備ができたら、ローカルリポジトリに作業内容をコミットしていきます。\
コミット、覚えてますか？

コミット（`commit`）とは、ある時点におけるフォルダとファイルのセーブデータです。\
セーブデータを作ることを「コミットする（`git commit`）」と言います。

初稿の執筆段階では、書き進めた原稿をコミットしていくことで進捗状況を記録できます。

![CommitLog1](img/Cap1_2-13_CommitLog1.png)

こんな感じです。\
**この記事**の執筆履歴です。\
図の右下、赤いハイライトは削った部分、緑のハイライトは書き加えた部分です。\
fixme が消えて、本文が書かれています。

図の真ん中、樹形図のエリアも見てみましょう。\
「説明」という列に書かれているテキストを「コミットメッセージ」と呼びます。\
コミットメッセージは、セーブデータに付け加えるメモです。どんな作業をしたのかを書いておくと、履歴を見渡すときに便利です。

必要に応じて「何をした」「何字書いた」とコミットメッセージに書けば、より具体的な進捗状況を記録できます。\
※スクリプトを利用すればコミットメッセージに字数まで自動的に記録するような芸当もできますが、この連載ではやりません。

校正・校閲の段階では、修正の概要と理由をコミットメッセージに記載しておくと、後で修正内容を再検討したり、元に戻したりするときの目印になるため便利です。

### 4.1 そのファイル、テキストですか？

それでは、あなたの手でコミットを作成しましょう。

…と言いたいところなのですが、まず確認したいことがひとつ。\
あなたが準備した原稿ファイルは、広義のテキストファイルですか？

Git は中身がテキストであるファイル（広義のテキストファイル）を扱うのに向いています。\
中身がテキストではないファイル（バイナリファイル）を扱うのは苦手です。具体的には拡張子が .docx とか .jtd とか .pages とかになっているファイルです。

特に理由がない限り、まずは原稿ファイルの形式をプレーンテキストファイル（.txt）にするのがいいでしょう。\
もちろんレイアウトや書式情報（メタデータ）は持てませんが、レイアウトや書式は組版の段階で考えればいいことです。\
原稿本文を執筆するときは本文の内容、つまりテキストに集中しましょう。

「それでも執筆段階から書式を意識したい」という人へ。\
テキストファイルでも装飾ができないわけではありません。\
本文に目印を書き込んでおけばいいのです。いままでは書式として設定していた内容を、あなたの手で明示的に書き込みます。

例えば、日本語の小説では、ルビ、圏点、縦中横といった装飾は執筆段階でも必要になりますね。\
「青空文庫記法」か「でんでんマークダウン」を利用して、装飾に必要な目印を付けましょう。\
例えば、青空文庫記法でルビを振る場合は

> 長女の髪は｜山吹《やまぶき》色だった。

と書くことで、山吹に《やまぶき》というルビを付けられます。

青空文庫記法はカクヨムや小説家になろうといったWEB小説投稿サイトと似たような装飾方法なので、これを期に覚えてしまいましょう。\
[青空文庫作業マニュアル【入力編】](https://www.aozora.gr.jp/aozora-manual/index-input.html#markup)\
[電書ちゃんのでんでんマークダウン - でんでんマークダウン](https://conv.denshochan.com/markdown)

ライターの人には見出しやリストが必要でしょう。\
見出しやリストを含む記事を執筆するなら、マークダウン記法（.md）で記述するのがオススメです。\
マークダウン記法とは、手軽に文章を装飾できる書き方です。\
参考：[Markdown記法 &middot; 日本語Markdownユーザー会](https://www.markdown.jp/syntax/)

ちなみに、この記事もマークダウン記法で書いています。\
片倉は Visual Studio Code というエディタで、本文の横にプレビューを表示する機能を使っています。便利ですよ。

![MarkdownPreview](img/Cap1_2-31_MarkdownPreview.png)

### 4.2 実際にコミットを作ろう

それでは、クローンしたリポジトリのフォルダで、新しいテキストファイルを作りましょう。\
既に準備してあるテキストファイルがあるなら、クローンしたリポジトリのフォルダに放り込みましょう。

![TextFile4Commit](/Chapter1/img/Cap1_2-15_TextFile4Commit.png)

今回の例では、 **StoryText.txt** と **MemoText.txt** を、 Git でバージョン管理するファイルとします。\
（厳密には .git フォルダがあるフォルダ以下、全てが Git の管理下に入ります）

ここからは Sourcetree の操作と CLI の操作を併記します。\
Sourcetree で行っている操作は、 CLI の操作で再現できるからです。

Sourcetree を使っている人は、Sourcetree を起動しましょう。\
CLI 操作の人は、 GitBash かターミナルを開きましょう。

Sourcetree を使っている人は、この記事の最初に作ったリポジトリのタブを選択しましょう。\
CLI 操作の人は、この記事の最初に作ったリポジトリの内部へ移動しましょう。\
`cd "クローンしたリポジトリのフォルダ"`

```bash
ktkr@KtkrPC MINGW64 ~
cd Documents/FaultofTheDreakEquation/
Sourcetree を使っている人は、樹形図にて **コミットされていない変更があります**というメッセージを「確認」できます。\
樹形図が表示されていない場合、左側のカラムにある「History」をクリックしてください。

![GitStatus](img/Cap1_2-16_GitStatus.png)

**コミットされていない変更があります** というのは、 Git の管理下にあるファイルが、最新のセーブデータ（コミット）から何かしらの変更があった、という意味です。

CLI 操作の人は、 `git status` で現在の状態を「確認」できます。

```bash
ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        MemoText.txt
        StoryText.txt

nothing added to commit but untracked files present (use "git add" to track)
```

**Your branch is up to date with 'origin/master'.** は、 Sourcetree における「**コミットされていない変更があります**」のメッセージと大意は同じです。\
つまり `git status` によって Sourcetree と同様に、現在の状態がどうなっているのか確認できるわけです。

メッセージの詳細を意訳すると

- 以下のファイルは Git の追跡対象になっていないよ
  - MemoText.txt
  - StoryText.txt

と言っています。

Git は .git フォルダが存在するフォルダより下の階層にあるフォルダとファイルを「管理対象」としますが、コミットしなければ「追跡対象」にはしません。追跡対象になっていないファイルはコミットに含まれないため、差分比較ができません。\
運用次第では意図的に特定のファイルを追跡対象に含めないこともあります。だいたい Git の設定で追跡対象から外すようにしますが。

状態を確認したら、次にコミットするファイルを選択します。\
Sourcetree なら画面下部にある「作業ツリーのファイル」からコミットするファイルを選びます。変更内容が右下の差分比較画面で見られます。\
コミットしていいなら、「選択をインデックスに追加」します。

「作業ツリー」とは、 Git の管理下にある、いま編集しているディレクトリのことです。\
「インデックス」とは、セーブデータ（コミット）を作る準備をするための場所です。\
「作業ツリーのファイル」を「インデックス」に「追加（`add`）」することで「ステージング」というセーブデータ待ちの領域に送ります。セーブデータ待ちの領域に送られたファイルは「ステージしたファイル」と呼びます。\
※厳密ではありませんが理解の促進を優先しています。

つまり、この段階ではセーブデータ（コミット）を作る準備をしています。\
セーブデータ（コミット）に含めるものはユーザーが自由に選べます。

![GitAdd1](img/Cap1_2-17_GitAdd.png)

CLI なら `git add` コマンドで、作業ツリーのファイルのうち、インデックスに追加（`add`）するファイルを選択します。\
つまり変更したファイルのうち、コミットするファイルを選択します。\
Sourcetreeで実施した操作と同じですね。

`git add "ファイルパス" "ファイルパス" ... "ファイルパス"`

```bash
ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git add StoryText.txt
```

Sourcetree の場合、インデックスに追加されたファイルは「Index にステージしたファイル」へ移動します。

![StagedFile](img/Cap1_2-18_StagedFile.png)

CLI の場合、インデックスに追加されたファイルは「Changes to be committed:」の所に表示されます。

```bash
ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   StoryText.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        MemoText.txt
```

意訳すると

- 以下のファイルがコミットに向けて追加されたよ
  - 新しいファイル：StoryText.txt
- 以下のファイルは Git の追跡対象になっていないよ
  - MemoText.txt

と言っています。

全てのファイルをコミットへ追加する対象に選ぶなら、 Sourcetree の「全てインデックスに追加」ボタンを押せば一発です。

![GitAddAll](img/Cap1_2-19_GitAddAll.png)

CLI の場合、`git add .` と入力すれば一発です。\
`.` （ドット）を忘れないでくださいね。これは「管理対象にある全てのファイル」を示しています。

```bash
ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git add .
```

全てのファイルを追加すると、 Sourcetree ではこんな画面になります。

![StagedFileAll](img/Cap1_2-20_StagedFileAll.png)

CLI の場合、 `git status` で同等の状態になっているかどうか確認します。

```bash
ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   MemoText.txt
        new file:   StoryText.txt
```

個別にファイルをインデックスに追加する場合と、全てのファイルを一括で追加する場合の、使い分けについて。

小説で例えると、1章を書いたテキストファイルと2章を書いたテキストファイルは別々にインデックスへ追加して、それぞれのセーブデータを作る、といった運用が便利でしょう。\
ただし、これも状況次第で変わります。1章の変更が2章の変更に関連しているなら、同じセーブデータにまとめたほうがいいでしょう。\
インデックスに追加するファイルをひとつずつ選択するか、全てのファイルを一気に追加するかは「そのときどのようなセーブデータを作りたいか」で使い分けます。

それでは、いよいよコミットしましょう。\
Sourcetree の場合、左上の、丸に十字の「コミット」ボタンをクリックします。\
画面下部にコミットメッセージを書きこむ欄が出現します。

![WriteCommitMessage](img/Cap1_2-21_WriteCommitMessage.png)

**1行目は樹形図の一覧に掲載されます**。簡潔に作業内容を記載しましょう。\
**2行目は空行にしてください**。\
2行目を空行にすると、3行目以降は補足的なメッセージと認識されます。

![WroteCommitMessage](img/Cap1_2-22_WroteCommitMessage.png)

コミットメッセージを確認して、内容に間違いがなければ右下の「コミット」ボタンをクリックします。

無事にコミットの作成が終わると、樹形図に新たなコミットが現れます。
![Committed](img/Cap1_2-23_Committed.png)

CLI の場合、 `git commit` と入力することでコミットの作成が始まりますが、**入力はちょっと待ってください**。

何も設定しないままだと、シェルのデフォルトエディタか、 vim が起動してコミットメッセージの編集が始まります。どちらも、たぶん使い慣れていない人のほうが多いエディタです。

Git の設定を変えれば、 Git の操作に関連して起動するエディタを好きなものに設定できます。

**今後も CLI で操作を続けるなら Visual Studio Code の使用を推奨します。**

詳細な理由は次回あたりに書くかもです。 VSCode とも呼びます。軽快に動作するテキストエディタで、 Git との相性も良い感じです。

テキストエディタの変更方法は他記事に譲ります。\
以下の記事あたりが参考になるでしょう。

- [Git とのテキストエディタの関連付け](https://help.github.com/ja/github/using-git/associating-text-editors-with-git)\
  最大手 GitHub のヘルプ記事。 Windows なら Notepad++ も悪くないと思います。
- [初git commit時にエディタが開かない（Pathエラー）解決方法。【VSCodeとGitHubの設定】](https://qiita.com/grca3/items/0771099a6750840721b1)\
  VSCode を Git 用のエディタに設定する方法と、エディタが開かない場合の原因・対処が簡潔に書かれています。

一応、今回は最低限必要な vim の操作を書きます。\
ですが、使いやすいテキストエディタでコミットメッセージを編集するのが一番です。\
設定したエディタが開いたらコミットメッセージを書いて、保存して、閉じれば、コミットが完了します。

では、 `git commit` と入力してください。\
テキストエディタを設定した人はそのテキストエディタが、設定していない人はおそらく vim が起動します。

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
# Your branch is up to date with 'origin/master'.
#
# Changes to be committed:
#       new file:   MemoText.txt
#       new file:   StoryText.txt
#
~
~
<ltofTheDreakEquation/.git/COMMIT_EDITMSG[+] [unix] (15:22 17/02/2020)1,0-1 全て
```

vim が起動しただけではコミットメッセージを編集できません。\
`i` キーを押すと `--挿入--` モードになります。

```vim

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
# Your branch is up to date with 'origin/master'.
#
# Changes to be committed:
#       new file:   MemoText.txt
#       new file:   StoryText.txt
#
~
~
~
~
~
~
~
<aultofTheDreakEquation/.git/COMMIT_EDITMSG[+] [unix] (15:22 17/02/2020)1,1 全て
-- 挿入 --
画面下部に「--挿入--」と出たら、編集できます。\
コミットメッセージを入力しましょう。

**1行目がメインのコミットメッセージと見なされます**。簡潔に作業内容を記載しましょう。\
**2行目は空行にしてください**。\
2行目を空行にすると、3行目以降は補足的なメッセージと認識されます。

```vim
書き出し。ファーストコンタクト。

人物を早出ししていきたいところ。
山吹色ってトパーズだっけ？
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
# Your branch is up to date with 'origin/master'.
#
# Changes to be committed:
#       new file:   MemoText.txt
#       new file:   StoryText.txt
#
~
~
~
~
~
~
~
~
<ofTheDreakEquation/.git/COMMIT_EDITMSG[+] [unix] (15:22 17/02/2020)4,40-27 全て
-- 挿入 --
```

コミットメッセージを書き終えたら、 `ESC` キーで挿入モードを終了します。\
`:w` と入力するとコミットメッセージを保存します。\
`:q` と入力するとコミットメッセージの編集を終了します。

無事にコミットの作成が終わると、こんな感じのログになります。

```bash
ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git commit
[master d59c9c7] 書き出し。ファーストコンタクト。
 2 files changed, 67 insertions(+)
 create mode 100644 MemoText.txt
 create mode 100644 StoryText.txt
```

最後に、リポジトリの状態を確認しましょう。

```bash
Ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

**nothing to commit, working tree clean** と表示されていれば、コミットするべき変更はありません。\
コミットするべき変更がないということは、今のフォルダとファイルの状態が全てセーブされている、ということです。\
つまり、何かの手違いでファイルを削除してしまったり、ファイルの内容を下手に変更してしまったりしても、 Git のコミット（＝セーブデータ）から復元（ロード）できる、ということです。

セーブデータを作ってゲームを進め、失敗したらセーブデータからロードしてやり直す。\
どうでしょう？　Git って、実はそんなに難しくないと思いませんか？

なお、今後、 `git status` は何かにつけて叩くコマンドです。\
Sourcetree を含む多くの GUI ツールは自動的に状態（ステータス）を更新しますが、 CLI で状態を確認するためにはユーザーが更新を指示しなければいけません。\
何かやる前に、とりあえず `git status` です。 Sourcetree を起動したりウィンドウを切り替えてアクティブにすることと、 `git status` を打つことは等価です。**手癖にしましょう**。

### 4.2 コミットをどんどん積んでいく

コミットの作り方は分かりましたね？\
ざっと手順を箇条書きにします。

1. 原稿を編集して上書き保存する
2. Sourcetree で状態を確認する（`git status`）
3. 変更したファイルを全てステージする（`git add .`）
4. ステージした内容を確認する（`git status`）
5. コミットする（`git commit`）

当面は、これらの作業を繰り返すだけで十分です。\
コミットメッセージをちゃんと書いておけば、以下のような疑問が浮かんだときにも、樹形図（コミットログ）を追いかけることでだいたい解決します。

> 「どのくらい進んだんだっけ」\
> 「あのときどんな文章を書いたっけ」\
> 「あの変更ってどこだったっけ」\
> 「どうして変更したんだっけ」

![CommitTree](img/Cap1_2-24_CommitTree.png)

CLI で操作している人は `git log` コマンドでコミットログを確認できます。
```bash
Ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git log
commit c8d60535c808908fd8957ab5acea87c05cd96491 (HEAD -> master)
Author: ktkraoichi <ktkrao1@gmail.com>
Date:   Mon Feb 17 16:10:21 2020 +0900
    朝ご飯を作って食べるシーン
commit b73526b0cd804b34c39966fd907480219f159272
Author: ktkraoichi <ktkrao1@gmail.com>
Date:   Mon Feb 17 16:08:38 2020 +0900
    リチャードがディアァを口説くシーン
commit 5f9aec4ebe6809f1b7c5c7c3d07bd88496348200
Author: ktkraoichi <ktkrao1@gmail.com>
Date:   Mon Feb 17 16:07:13 2020 +0900
    出会い -> 移動
```
スマートに表示したいときは、次のようなオプションを付けましょう。
`git log --oneline`
```bash
Ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git log --oneline --decorate
c8d6053 (HEAD -> master) 朝ご飯を作って食べるシーン
b73526b リチャードがディアァを口説くシーン
5f9aec4 出会い -> 移動
e71cb84 師弟ズの出会いを書いた
bc2451e 全部書き直し。一人称で書くことにした。
72c960b 序盤の表現をちまちま修正
a23bf9c 会話と描写を追記。今後の展開をメモした。
de8b1ca 有機ポリシランを生成することにした。他、動作や描写を追加。
d59c9c7 書き出し。ファーストコンタクト。
485950e (origin/master, origin/HEAD) Initial commit
```
### 4.3 いつコミットすればいいのか（コミット粒度）
コミットをどんどこ積んでいくと、そのうち「いつコミットすればいいんだろう？」という疑問が浮かぶことでしょう。\
これは「コミット粒度」といって、プログラマな人たちの間でもわりと話題になります。ときどき戦争が起こります。
文章の執筆に限れば、片倉は次のような感じでいいのではないかと考えています。
- 基本思想：元に戻したくなるタイミングでコミットする
  - 例1：その日の執筆分をコミットする
  - 例2：シーンやエピソードの区切りがついたらコミットする
  - 例3：表記揺れをひとつ統一したらコミットする
コミットは作業内容のセーブデータです。\
ゲームをプレイするとき、セーブデータは「ここからリスタートしたいな」というタイミングでセーブしますよね？\
具体的には、ボス直前だったり、なにかのギミックをクリアしたり、ゲームに疲れて中断するときだったり。
ソースコードの場合は、プログラムの挙動に影響を与えるのでコミット粒度をよくよく考えなければいけません。
ですが、文章執筆におけるコミット粒度は人それぞれ。\
慎重な人はこまめにセーブするでしょうし、面倒くさがる人はプレイを終える前だけセーブするでしょう。\
いずれにせよ、後悔しないタイミングでコミットすればよい、と片倉は思います。\
ただし、コミットメッセージは後から探しやすいようにしましょうね。
「文章執筆ならこんなコミット粒度がいいよ！」というご意見がありましたら、ぜひコメントに書き込んでください。参考にします。
### 4.4 コミット間の差分を確認する
あるコミットと別のコミットの差分を見たいときは `git diff` コマンドを使います。
`git diff <コミットID> <コミットID>`\
コミットIDは `git log --oneline` で表示した "c8d6053" とか "b73526b" とかの、16進数で表記された番号のことです。

![GitDiff](img/Cap1_2-25_GitDiff.png)

`q` キーで diff の確認を打ち切れます。
…これは…ちょっと分かりづらいですね。\
Git が最初から持っている差分比較機能は、日本語の文章に対しては弱めです。
Sourcetree の場合、 `Ctrl` キーを押しながら、比べたいコミットを選択することで、差分を確認できます。
![SourcetreeDiff](img/Cap1_2-33_SourcetreeDiff.png)
…これも Git 標準の差分比較機能と大差ないですね。
もっとイケてる感じの差分比較ツールを利用することもできますが、これは次回に譲ります。
ひとまず、どんどんコミットを積みましょう。
長くなりましたが、やっと最後です。\
もうちょっと頑張りましょう。

コミットは、ローカルリポジトリに積まれていきます。\
ディスクが壊れてしまったり、お使いのパソコンが爆発したりすると、いままで積み上げてきたコミットはオシャカになります。ご破算です。頑張って書いてきた卒論や修論はイチから書き直しです。

Q. どうすればいい？\
A. ローカル以外にもリポジトリの保管場所を確保する

そうです。セーブデータお預かりサービスを利用します。 Switch オンラインとか PS Plus とかでよく使うアレです。\
え、ゲームしないからピンとこない？　では iCloud とか Google フォトのバックアップ機能あたりを想像してください。アレです。

というわけで、冒頭で作成した GitHub のプライベートリポジトリにプッシュしましょう。\
ローカルにあるセーブデータのバックアップを GitHub にも複製する、ということです。

Git では、セーブデータのバックアップをインターネットへ送信することを「プッシュ（push）」と呼びます。\
※厳密ではありませんが理解の促進を優先しています。

まずは状態を確認しましょう。\
Sourcetree の画面はこんな感じです。
![CommitTree](img/Cap1_2-24_CommitTree.png)
CLI で操作している人は `git log --oneline` で確認しましょう。
```bash
Ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git log --oneline
c8d6053 (HEAD -> master) 朝ご飯を作って食べるシーン
b73526b リチャードがディアァを口説くシーン
5f9aec4 出会い -> 移動
e71cb84 師弟ズの出会いを書いた
bc2451e 全部書き直し。一人称で書くことにした。
72c960b 序盤の表現をちまちま修正
a23bf9c 会話と描写を追記。今後の展開をメモした。
de8b1ca 有機ポリシランを生成することにした。他、動作や描写を追加。
d59c9c7 書き出し。ファーストコンタクト。
485950e (origin/master, origin/HEAD) Initial commit
```

`master` というラベルが、樹形図の先頭にある「朝ご飯を食べるシーン」というコミットにくっついていますね。\
これはローカルリポジトリの先頭にあるコミットです。

`origin/master` というラベルはというと「Initial commit」というコミットにくっついています。\
`origin` というのはリモートリポジトリのことです。\
つまり、今のリモートリポジトリには**まだ「Initial commit」というコミットしか存在しません**。\
いまこの状態では、リモートリポジトリはローカルリポジトリに比べて「遅れて」います。

ローカルリポジトリのコミットをリモートリポジトリにプッシュすることで、ローカルリポジトリとリモートリポジトリの内容が一致します。

※ Git 分かる人へ\
今回は `fetch` には触れません。ブランチの概念を理解する必要があること、一人が一つの端末から `commit` と `push` を繰り返す分には `fetch` しなくても問題は起きないこと、などが理由でs。

Sourcetree を使っている人は丸に↑の字の「プッシュ」ボタンをクリックしてください。

![GitPush](img/Cap1_2-27_GitPush.png)

今のところ `master` というブランチだけのはずなので、諸々の項目は特に気にしなくて大丈夫です。\
「プッシュ」ボタンをクリックしましょう。

Sourcetree がぐるぐる動き…

![GitPushed](img/Cap1_2-28_GitPushed.png)

完了したら、変化した樹形図にご注目。\
`master` と `origin/master` というラベルが同じコミットに付いていたら、プッシュは無事に完了です。

CLI で操作している人は、 `git push` と打ちます。

```bash
Ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 9 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

Ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$ git push
Enumerating objects: 29, done.
Counting objects: 100% (29/29), done.
Delta compression using up to 4 threads
Compressing objects: 100% (28/28), done.
Writing objects: 100% (28/28), 29.08 KiB | 561.00 KiB/s, done.
Total 28 (delta 14), reused 0 (delta 0)
remote: Resolving deltas: 100% (14/14), done.
To https://github.com/ktkraoichi/FaultofTheDreakEquation.git
   485950e..c8d6053  master -> master

Ktkr@KtkrPC MINGW64 ~/Documents/FaultofTheDreakEquation (master)
$
```

`git status` は手癖ですよ、手癖。

これで、ディスクが壊れてしまったり、お使いのPCが爆発してしまっても大丈夫。\
リモートからリポジトリを引っ張ってくれば元通りになります。

無事にプッシュまで完了しましたか？\
ローカルの `master` と、リモートの `origin/master` のラベルは同じ位置にありますか？

大丈夫なことを確認できたら、あなたはとてもとても凄い！\
自分を褒めましょう！　なにせここまでで2万字くらいあります！\
読破して、手を動かしただけでも凄い！\
無事に終えられたなら、もっともっと凄い！

これで変更履歴を確認できますし、いきなりPCが爆発しても大丈夫です。\
誰が何を変更したのか分かりますし、手元のファイルが壊れてもリモートから引っ張ってくれば元通りです。

Git と GitHub の威力が本当に発揮されるのはもう少し先ですが、

- リモートリポジトリを作り
- コミットして
- プッシュする

という基本ができるようになったことはとても喜ばしいことです。\
どんどんコミットして、どんどんプッシュしましょう！\
（`git status` はターミナル開いたらとりあえず打ちましょう）

### 5.1 Sourcetree に「コミットをすぐにプッシュする」ってあるけど…

これのことですね？

![CommitAndPushImmediately](img/Cap1_2-29_CommitAndPushImmediately.png)

やめておきましょう。

理由は色々あります。\
コミットやプッシュに失敗することは結構あります。\
慣れないうちは失敗の原因がコミットなのかプッシュなのか、よく分からないでしょう。\
特にリモートの操作には危険な内容もあるので、よく分からないまま触るのは厳禁です。\
意識的に「コミットする」と「プッシュする」を分けて操作しましょう。\
エラーメッセージを落ち着いて読めば、解決手段をネットで検索することも難しくはありません。

また、「すぐにプッシュしない」ことにはメリットもあります。\
すぐにプッシュしない場合、「コミット内容の確認」という手順を明示的に確保できます。

コミットしてから\
「あ、誤字ひとつ見つけた」\
のような、ごく軽微な修正をしたくなるケースは、しばしばあります。\
軽微な修正のためだけにコミットをひとつ作ってしまうと、コミットログをざっと眺めるときに邪魔になります。

次回で詳しく解説しますが、 Git では「直前のコミットを作り直す」という操作ができます。\
コミットの作り直しにより、ファイル内容の再変更、新しいファイルの追加、コミットメッセージの変更などができます。

コミット内容を確認する手順を確保するために、\
「すぐにプッシュする」\
のオプションは外しておきましょう。
これであなたは Git を利用するメリットを少し受けられるようになりました。\
いっぱい説明しましたが、要するに「こまめにセーブしながら原稿を進めましょう」というだけのことです。簡単でしょう？

では、次はブランチの操作に取り組みましょう！\
ブランチとプルリクを駆使して爆速校正ライフを手に入れましょう！

…と言いたいところなのですが、まずはローカルの状態を確認して、コミットして、プッシュする、という作業に慣れてください。\
CLI で操作している人は `git status` で状態を確認することもお忘れなく。

次回は

1. ちょっとしたミスを `git commit --amend` で書き換えてしまう
2. `restore` で過去のファイルを掘り起こしてみる
3. 便利な差分比較ツールの紹介

の3点です。

ローカルのコミットを閲覧したり、ちょいといじったりする、 Tips をメインに解説していきます。
### 7.1 「クライアントが Word 提出を希望しているんだが」という人へ
ご安心ください。\
マークダウンで書いたファイルは Word ファイル（.docx）に変換できます。\
Pandoc という強力なドキュメント変換ツールを使いましょう。\
Pandoc については多くの方が使い方を紹介しています。ググってください。
- Qiita の先達\
  [多様なフォーマットに対応！ドキュメント変換ツールPandocを知ろう
](https://qiita.com/sky_y/items/80bcd0f353ef5b8980ee)
- 先達による「Pandoc User’s Guide」の日本語訳\
  [Pandoc ユーザーズガイド 日本語版 - Japanese Pandoc User's Association](http://sky-y.github.io/site-pandoc-jp/users-guide/)
Pandoc わかんないって人に向けて
- GitHub とかでマークダウンファイルのプレビューを見る
- プレビューから必要な範囲をコピーする
- Word に貼りつける
- 整形する

という力技もご紹介しておきます。\
あんまりオススメしません。

### 7.2 えー、ブランチの解説してよ

ライター案件の〆切が迫っている ＆ 確定申告に着手さえしていない\
というヤバい状況なので、解説の負担が大きい「ブランチ」についてはもう少し先にさせてください。\
スミマセン…

- Git の本質は差分比較機能付きのデータベースである
- データベースの実装がハッシュツリーである
- ブランチとはコミットに付いたラベルである

といった話も含めてやるので、図とか作るのに時間がかかるのです。\
ご容赦。

### 7.3 あれ、 SSH の解説やるって…

すみません。
一旦 GitHub の認証を通したら `push` するときも認証いらないんでした。\
https 認証を滅多に使わないので忘れてました。

で、 SSH なんですが、そもそも扱いがちょいとデリケートです。\
Git の本質からは外れる、ということもありますので、手空きになったら取り扱います。
- 先達の良記事\
  [お前らのSSH Keysの作り方は間違っている](https://qiita.com/suthio/items/2760e4cff0e185fe2db9)