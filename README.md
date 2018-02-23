# エスコフィエ『料理の手引き』新訳作業用リポジトリ #



## 「チラ見」ファイルの閲覧、ダウンロード ##

  * [ ] 「チラ見」用のPDFは<>code の最上位ディレクトリにあります。ファイル名は escofier-le-guide-culinaire-octavo.pdf です。拡張子にご注意ください。最後が .tex となっているファイルはPDF組版用のものでTeXという組版言語を用いて書かれています。もしお読みになって目まい、頭痛になったとしても自己責任となりますのでご注意を。PDFファイルはブラウザ上でも直接開けるみたいですが、動作がとても遅い可能性があります。

本文は1段組み、レシピは二段組です。PDFの設定上は八折りという判型に準拠して、縦221mm横142mmにしてあります。パソコンやタブレットだと読みやすいでしょう。スマートフォンの場合は適宜拡大しないと読みづらいかも知れません。


## 編集協力の方法 ##

編集協力者は常時募集中です。Githubのシステム上、アカウントをお持ちであればどなたでも編集にご協力いただけます。

Markdownファイル（.md）が作業ファイル=原稿です。

[**Pandoc Extended Markdown**](https://pandoc.org/MANUAL.html#pandocs-markdown)いう書式を用いており（[**日本語版はこのリンクの上から1/3くらいのところ**](http://sky-y.github.io/site-pandoc-jp/users-guide/)、ただし内容が古いので出来るだけ英語版を参照してください）、このサービスで標準とされている Github Flavored Markdown に準拠していない部分があるため、ブラウザ上でのプレビューは正しく表示されないことがほとんどです。

原稿そのものを適切にプレビューするには、Pandoc Extended Markdown に対応したエディタが必要です。（Atomいうエディタに追加パッケージで対応するものがあったと思います）。

**編集協力者は、番号（=章番号）で始まるディレクトリ内のMarkdownファイルに対してのみ編集してコミットするようにしてください**。（以下にファイル名を列挙しておきます）

命名規則は

章番号-節番号-ppページ範囲.md

* 00-avant-propos/00-avant-propos.md
* 01-sauces/01-01-pp1-12.md
* 01-sauces/01-02-pp13-17.md
* 01-sauces/01-03-pp18-27.md
* 01-sauces/01-04-pp28-41.md
* 01-sauces/01-05-pp42-46.md
* 01-sauces/01-06-pp47-52.md
* 01-sauces/01-07-pp53-57.md
* 01-sauces/01-08-pp58-62.md
* 01-sauces/01-09-pp63-67.md

**これらのファイルに対してだけ変更をコミットしてください。**


PDFは適時マージされます。単に組版イメージ確認のためであり、「チラ見」用です。

それ以外のファイル（TeX関連が主です）は、Lualatex を分る方以外は触らないようにご注意ください。目まいがするか、頭が痛くなっても責任は負えません。

原稿ファイル（.md）には時折\{\#fonds-blanc-volaille\} のようなものが見出しにありますが、これはPDFやHTML、EPUBで内部リンクを張るための「ラベル」です。原書の項目名を、すべて小文字」にしてアクサンなし、ハイフンでつないでいます。


### Markdownファイル=原稿はブラウザ上で作業可能です ###

ブラウザでこのリポジトリを開き、ソース>目的の章のディレクトリ>作業ファイル、と進んでください。

.md ファイルをクリックして開くとMarkdownのプレビューモードで表示されます。右上にある「編集」=鉛筆のマークをクリックして編集モードに移行します。間違ってもその隣の「ゴミ箱」をクリックしないでください。

この状態で**誤字、脱字、明らかなミスについては直接書き込んでください**。その後、

1. 上のほうにある Preview Changes を押して変更内容を確認します。環境によってはちょっと待たされることがあります。
2. OKであれば、スクロールして下の方にある Create a new branch for this commit and start a pull request. の左のラジオボタンが選択されていることを確認し、上のコメント覧に変更内容等を書いてください。
3. 大きなボタン Commit Changes を押します。
4. 画面が変わり、Create a Pull Request なんたらという表示が出るので、再確認ボタンを押すと「プルリクエスト」が作成されたことになります。この時点ではこのリポジトリのファイルに変更は加えられていません。要するに「変更の提案」ということです。このときにコメント欄があります。これが主な議論の場となりますので活用してください。
5. プルリクエストがあると、僕が変更内容を確認し、妥当と判断すればマージ（ファイルに取り込むこと）します。

#### ローカルルール #####

* 数字は一桁のものも半角数字を用いてください（全角は用いないでください）。前後にスペースを入れる必要はありません（とりわけ禁則文字、役物の一部が自動処理されずに問題が発生することが確認されました）。
* ただし、単位を表す ml, dl, L, g, kg, mm, cm なども半角文字を使いますが、半角数字の直後には半角スペースを挟んでください。（例） ワイン1 dl、

これらはTeXで処理する際に、自動的に適当に文字間を調整して表示されます。


#### 注釈の編集、追加方法 ####

すでにある注釈に変更を加える場合は、直接書き込んでください。その直後に\[\](○○変更)のようにコメントがあるとわかりやすいでしょう。

あらたに注釈を追加する場合、すでにある番号とダブってしまうとエラーの原因になりますので、

    本文[^15]本文本文[^15bis]本文本文本文
	本文本文本文。
	
	[^15]: すでにある注釈だけどここは変更[](20180129○○変更)注釈文の続き
	
	[^15bis]: あらたに追加した注釈
	
のように、直前の注釈番号にbisをつけてください。すでに直前のものにbisがついている場合は、bis2、bis3のようにして、かならず番号がダブらないようご注意ください。また、注釈は対象の段落の直後がわかりやすくて便利です。

#### TeX命令文が含まれています ###

基本的に、TeXという組版プログラム群を使う前提の md ファイルです。そのため、markdown の書式ではないTeX命令の行がしばしばあり、プレビュー状態でも表示されてしまいます。

\index{そーす@ソース!しょふろわちゃいろ@---・ショーフロワ(茶色)}
\index{しょふろわ@ショーフロワ!そーす(ちゃいろ)@ソース・--- (茶色)}
\index{sauce@sauce!chaud-froid brune@--- Chaud-froid brune}
\index{chaud-froid@chaud-froid!sauce brune@Sauce --- brune}

あるいは

\newpage

あるいは

文章\ruby{漢字}{ふりがな}

など。


##### レシピ名の前アキ指定もTeX書式が入っています #####

レシピの日本語名の前に、ほとんどの場合、

\maeaki

が入っています。レシピ名と前の段落との間隔の指定用に作ったTeXの独自命令です。


##### 分数の表示もTeX表記にしました #####

分数の表記には独自のTeX命令を使います

* 1/2 = \undemi{}
* 1/3 = \untiers{}
* 2/3 = \deuxtiers{}
* 1/4 = \unquart{}
* 3/4 = \troisquarts{}
* 1/5 = \uncinquieme{}
* 2/5 = \deuxcinquiemes{}
* 3/5 = \troiscinquiemes{}
* 4/5 = \quatrecinquiemes{}
* 1/6 = \unsixieme{}
* 5/6 = \cinqsixiemes{}


**TeXに不慣れな方はバックスラッシュ\で始まるこれらの表現には触れないようにしてください**。お願いします。

#### 編集コメント ####

短かいコメントは**文中に**、少し長いなら、該当段落の下にカラ行を多めに入れてあるので、そこに、

    [](コメント)

として書いてください。\[と\]の間はスペースなし。**半角記号**です。カッコも必ず**半角**にしてください。多少長くなっても大丈夫ですが、余分な改行は入れないほうがdiffが見やすいので、改行しないようお願いします。

編集モードでこの行の下を見るとコメントの実例が見られます。
[](これはコメントの例です)

このようにして書いたコメントは「プレビュー」モードで表示されなくなりますが、編集モードとdiff表示において表示されます。

長いコメントは、コミットする際（後述）にコメント欄がありますので、そこでも大丈夫です。


### コミット ###

とても**大事なこと**なので2度書きます。

ブラウザ上で編集した場合、作業後に

1. 上のほうにある Preview Changes を押して変更内容を確認します。環境によってはちょっと待たされることがあります。
2. OKであれば、スクロールして下の方にある Create a new branch for this commit and start a pull request. の左のラジオボタンが選択されていることを確認し、上のコメント覧に変更内容等を書いてください。
3. 大きなボタン Commit Changes を押します。
4. 画面が変わり、Create a Pull Request なんたらという表示が出るので、再確認ボタンを押すと「プルリクエスト」が作成されたことになります。この時点ではこのリポジトリのファイルに変更は加えられていません。要するに「変更の提案」ということです。このときにコメント欄があります。これが主な議論の場となりますので活用してください。
5. プルリクエストがあると、僕が変更内容を確認し、妥当と判断すればマージ（ファイルに取り込むこと）します。

### Markdownプレビューモードでの注番号について ###

Githubでのプレビューモードでは、注が正しく表示されません。ダウンロードしてMarkdown対応エディタのプレビューを使うか、pandocで適宜変換してください。


### ブラウザ上で編集する際の注意 ###

ブラウザ上で編集する場合、「コミット」が完了するまで変更した内容が保存されません。僕はよくやってしまうのですが、誤ってページのリロード、バックなどしてしまうと、それまでの編集内容が全て失なわれてしまいます。

そのため、多少煩雑になっても、1ファイルまとめて全部徹底的に、ではなく、数回に分けて編集、コミットするほうが安全です。

あるいは、エディタにコピペして作業し、それを戻していただいても結構ですが、その場合は、**余計な空白行などが入らない**ようご注意ください。Diffによる変更点の比較がうまくいかなくなりますので。

もっとも、エディタで作業できるのであれば、Githubアプリをお使いいただくほうが便利だと思います。

### 見出しの階層 ###

* \# 章(ソース、ガルニチュール etc）
* \#\# 節（基本ソース、茶色い派生ソース etc.）
* \#\#\# 節のフランス語表記
* \#\#\#\# レシピ名
* \#\#\#\#\# レシピ名のフランス語表記
* \#\#\#\#\#\# さらにその下のもの（原注など）



<br /><br /><br />
©Manabu GOTO 2018 All Rigths Reserved
