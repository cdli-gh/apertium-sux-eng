Sumerian and English: `apertium-sux-eng`
===============================================================================

This is an Apertium language pair for translating between Sumerian and
English. What you can use this language package for:

* Translating from Sumerian to English
* Morphological analysis of Sumerian and English

The basic morph analyzer of sumerian can be found here - \
https://github.com/cdli-gh/apertium-sux

The english monolingual dictionary can be found here - \
https://github.com/apertium/apertium-eng

<br>

Sumerian Data Source
----------------------------
The [mtaac_gold_corpus](https://github.com/cdli-gh/mtaac_gold_corpus) is used to build the monolingual dictionary. 

For Data-Preprocessing refer [sux_preprocessing.ipynb](sux_preprocessing.ipynb)

**Note -**  The current sux(Sumerian) morph analyzer uses vocab along with tags as it is, as specified in mtaac_gold_corpus. The current sux analyzer can only produce basic morphological analysis. After development this will be replaced by - \
https://github.com/m-sameer/sumor 

<br/>


Sumerian Morph Details
-----------------------------
MTAAC and CDLI Documentation - \
https://cdli-gh.github.io/guides/guide_tagsets.html

ETCSRI's Morphological Parsing - \
http://oracc.museum.upenn.edu/etcsri/parsing/index.html


Morphological Chart - \
https://docs.google.com/spreadsheets/d/1y0_y9HDQNwH0VqDCjjYuUpFsugw4GEybu6Pu01I_D9c/edit#gid=0

Tag Translations - \
[data/Morph_info_and_samples/tag-translation.tsv](data/Morph_info_and_samples/tag-translation.tsv)


<br/>

Requirements
---------------------------------------------------------------------

You will need the following software installed:

* autoconf
* automake
* pkg-config
* lttoolbox (>= 3.5.1)
* apertium (>= 3.6.1)
* vislcg3 (>= 1.3.1)
* apertium-sux
* apertium-eng

For more details of dependencies check Apertium Installation:
https://wiki.apertium.org/wiki/Installation


**Other dependencies to evaluate the translation models**

* nltk (check [NLTK_BLEU_SCORE](https://www.nltk.org/_modules/nltk/translate/bleu_score.html)  for more information)


<br>


Compiling
-------------------------------------------------------------------------------

Given the requirements being installed, you should be able to just run:

```console
$ autoreconf -fvi
$ ./configure
$ make
# make install
```

You can use `./autogen.sh` instead of `autoreconf` and `./configure` in case you're compiling
from source. If you installed any prerequisite language packages using a
`--prefix` with `./configure`, make sure to use the same `--prefix` when running
`./configure` here.

If any of this doesn't make sense or doesn't work, see https://wiki.apertium.org/wiki/Install_language_data_by_compiling


<br>

Testing
-------------------------------------------------------------------------------

If you are in the source directory after running make, the following
commands should work:

```console
$ echo "e2 lugal-la mu-un-du3" | apertium -d . sux-eng
house of king he built
```

After installing somewhere in `$PATH`, you should be able to do e.g.

```console
$ echo "e2 lugal-la mu-un-du3" | apertium sux-eng
house of king he built
```

### Translation Testing
For the testing we are using the **dev** data from the [mtaac_syntax_corpus](https://github.com/cdli-gh/mtaac_syntax_corpus) \
For the python script or testing on a new data checkout [sux_apertium_test.ipynb](sux_apertium_test.ipynb) \

The evaluation is done using the BLEU metric and the current rule based model score - \
**RBMT BLEU SCORE -** 9.0025  
\* with weightage (0.75,0.25,0,0) over n-grames

<br>


Files and data
-------------------------------------------------------------------------------

* [`apertium-sux-eng.sux-eng.dix`](apertium-sux-eng.sux-eng.dix) - Bilingual dictionary
* [`apertium-sux-eng.sux-eng.rtx`](apertium-sux-eng.sux-eng.rtx) - Structural transfer rules for translating into English
<!-- * [`apertium-sux-eng.eng-sux.rtx`](apertium-sux-eng.eng-sux.rtx) - Structural transfer rules for translating into Sumerian
* [`apertium-sux-eng.sux-eng.lrx`](apertium-sux-eng.sux-eng.lrx) - Lexical selection rules for translating into English
* [`apertium-sux-eng.eng-sux.lrx`](apertium-sux-eng.eng-sux.lrx) - Lexical selection rules for translating into Sumerian
* [`modes.xml`](modes.xml) - Translation modes -->






For more information
-------------------------------------------------------------------------------

* https://wiki.apertium.org/wiki/Installation
* https://wiki.apertium.org/wiki/Apertium-recursive/Formalism

<!-- 
Help and support
-------------------------------------------------------------------------------

If you need help using this language pair or data, you can contact:

* Mailing list: apertium-stuff@lists.sourceforge.net
* IRC: `#apertium` on irc.oftc.net (irc://irc.oftc.net/#apertium)

See also the file [`AUTHORS`](AUTHORS), included in this distribution. -->
