# GoogleBooks_Ngram_Viewer_a 

使い方

# 基本 編
- Wildcard Search　"*"
	> University of *
	> 
	>これで University of にマッチする単語が得られる。
    >ただしtop10しか表示されない。
    >また接頭辞接尾辞を指定したい場合？は "\_STRAT\_ / \_END\_" で指定を行う。

- Inflection Search "_INF"
    > book_INF a hotel
    > 
	>これでbook~と語尾が変化するものをすべて検索できる。
    >例の中には "book", "booked", "books", "booking"が含まれていた
    >検索クエリの中には一つか使用できないので注意

- Case Insensitive Search 
	> デフォルトでは大文字と小文字を区別した検索が行われているが、検索クエリの欄を触ると、大文字と小文字を区別しない検索ができる。
    > 例えば「 Dupont（All）」を右クリックすると、「DuPont」、「Dupont」、「duPont」、および「DUPONT」の4種類が表示される。
	>
    >検索では以上の3つを自由に組み合わせることはできず、一つしか使用できない。

- Part-of-speech Tags "品詞タグ"
    > tackle_VERB , tackle_NOUN
    > 品詞を書くことによって\*よりも細かい検索ができる。
   
#### タグリスト
>単独で使用しないもの
>\_NOUN\_		名詞
>
>\_VERB\_   動詞
>
>\_ADJ\_	形容詞
>
>\_ADV\_	副詞
>
>\_PRON\_	代名詞
>
>\_DET\_	determiner or article　　限定詞(the)
>
>\_ADP\_	an adposition: either a preposition or a postposition　接続詞？
>
>\_NUM\_	numeral　数詞
>
>\_CONJ\_	conjunction　接続詞
>
>\_PRT\_	particle　語形変化のない語? 接続詞との違いがわからない(on,a,an,... )

>単独で使用するタグ
>
>\_ROOT\_	root of the parse tree	These tags must stand alone (e.g., _START_)
>
>\_START\_	start of a sentence
>
>\_END\_	end of a sentence

# 組み合わせ方&その例 編
- read "xxx" book の限定詞を考える
    > read * _DET book とすることで、 
    >
	> read the_DET book
    > 
	> read a_DET book
	>
    >read this_DET book
	>
    >read that_DET book
	>
    >read any_DET book
	>
    >read every_DET book
	>
    >read some_DET book
	>
    >read no_DET book
	>
    >read another_DET book
	>
    >read each_DET book
	>
    >をすべて検索でき、これらを分離することもできる。
    
- book"語形変化" "名詞" を考える
    > book_INF \_NOUN\_ とすることで、
    >book \_NOUN\_
    >
    >books \_NOUN\_
    >
    >booking \_NOUN\_
    >
    >booked \_NOUN\_
    >
    >のすべてを検索できる。

- cook+"xxx"のような言葉と動詞の混用を考える
  	> cook\_\* とすることで、
    >
    >cook_VERB, cook_NOUN を同時に検索できる。

- cook_INF, cook_VERB_INFでは、
    >cook
>cooking
>
>cooked
>
>cooks
>
>cooked_VERB
>
>cooking_VERB
>
>cook_VERB
>
>cooks_VERB
>が検索できる。

- \_START\_, \_END\_ について
    > \_START\_ President Truman
\_START\_ President Lincoln
\_START\_ President Harding と検索できる(*との違いは？)

- デザートおいしい！のような語と語に関係性のある(依存している)文章を検索したいとき
    > dessert=>tasty と =>を用いる

- \_ROOT\_　について
    > s





