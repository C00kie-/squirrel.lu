## start with nltk (Natural Language Toolkit)

```
$pip install --user U nltk
```

Start python3 on your terminal:
```
$python3 
>>> import nltk
>>> nltk.download('popular') 
```
see https://www.nltk.org/nltk_data/ 

 try to import common corpus
 ```
 >>> nltk.download('brown')
[nltk_data] Downloading package brown to /Users/poknyen/nltk_data...
[nltk_data]   Unzipping corpora/brown.zip.
True
```

if you want to see corpora status and download some specific: 
````
>>> nltk.download()
NLTK Downloader
---------------------------------------------------------------------------
    d) Download   l) List    u) Update   c) Config   h) Help   q) Quit
---------------------------------------------------------------------------
Downloader> l

Packages:
  [ ] abc................. Australian Broadcasting Commission 2006
  [ ] alpino.............. Alpino Dutch Treebank
  [*] averaged_perceptron_tagger Averaged Perceptron Tagger
  [ ] averaged_perceptron_tagger_ru Averaged Perceptron Tagger (Russian)
  [ ] basque_grammars..... Grammars for Basque
  [ ] biocreative_ppi..... BioCreAtIvE (Critical Assessment of Information
                           Extraction Systems in Biology)
  [ ] bllip_wsj_no_aux.... BLLIP Parser: WSJ Model
  [ ] book_grammars....... Grammars from NLTK Book
  [ ] brown............... Brown Corpus
  [ ] brown_tei........... Brown Corpus (TEI XML Version)
  [ ] cess_cat............ CESS-CAT Treebank
  [ ] cess_esp............ CESS-ESP Treebank
  [ ] chat80.............. Chat-80 Data Files
  [ ] city_database....... City Database
  [*] cmudict............. The Carnegie Mellon Pronouncing Dictionary (0.6)
  [ ] comparative_sentences Comparative Sentence Dataset
  [ ] comtrans............ ComTrans Corpus Sample
  [ ] conll2000........... CONLL 2000 Chunking Corpus
  [ ] conll2002........... CONLL 2002 Named Entity Recognition Corpus
Hit Enter to continue: 
  [ ] conll2007........... Dependency Treebanks from CoNLL 2007 (Catalan
                           and Basque Subset)
  [ ] crubadan............ Crubadan Corpus
  [ ] dependency_treebank. Dependency Parsed Treebank
  [ ] dolch............... Dolch Word List
  [ ] europarl_raw........ Sample European Parliament Proceedings Parallel
                           Corpus
```
````

Corpora installed are those with the * between [ ]
So if you want to install a specific corpus specify the name of the corpus:
````
nltk.download(city_database)
````

to open your own corpus : 

```
>>> f=open('your-corpus.txt', 'r')
>>> text=f.read()
>>> text1=text.split()
```

text.split() will split all the words in your file that NLTK can access and read.
text1 is a **python list**, not a text

see the types of your variables:
````
>>> type(text)
<class 'str'>
>>> type(text1)
<class 'list'>
````

clean corpus from non alpha-numeric characters:
````
sorted([w for w in set (text1) if w.isalpha()])
````

Searching for something specific? : list words in corpus who starts with a specific letter or chain of characters:
```
>>> sorted([w for w in set (text1) if w.startswith('home')])
['home', 'home!', 'home!!!', 'home"', 'home)', 'home,', 'home,"', 'home,”', 'home-buyer', 'home-free.', 'home-made', 'home-office', 'home.', 'home.[9]', 'home/end', 'home?', 'homebrew', 'homebrewing', 'homebuyer', "homebuyer's", 'homebuyers.', 'homebuyer’s', 'homebuying', 'homegrrl)', 'homeland', 'homeowner', 'homeowners', 'homeownership', 'homepage', 'homepage,', 'homepage.', 'homes', 'homes,', 'homes.', 'homes."', 'homes.”', 'homes;', 'homes”', 'homework', 'homework.', 'home’', 'home’s']
>>> 

```

Have fun!
