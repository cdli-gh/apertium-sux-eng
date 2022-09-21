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


<br/>


Requirements
------------------------------------------------------------
---------

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



**Other Requirments to run NMT and translation comparision**
* nltk 
* pandas
* tqdm
* numpy
* PyTorch
* OpenNMT-py

refer this for further details - [Semi-Supervised-NMT-for-Sumerian-English](https://github.com/cdli-gh/Semi-Supervised-NMT-for-Sumerian-English)


<br>



Sumerian Data Source
---------------------------------------------
-------
- [mtaac_gold_corpus](https://github.com/cdli-gh/mtaac_gold_corpus)
- [mtaac_syntax_corpus](https://github.com/cdli-gh/mtaac_syntax_corpus/tree/master/parallel/consolidated) \
For the monolingual dictionary. 

For Data-Preprocessing refer - [sux_dict_prepration.ipynb](Notebooks/sux_dict_prepration.ipynb)

**Note -**  The current sux(Sumerian) morph analyzer uses vocab along with tags as it is, as specified in mtaac_gold_corpus. The current sux analyzer can only produce basic morphological analysis. After development of morphological analyzer this can be replaced by - [**cdli-gh/sumor**](https://github.com/cdli-gh/sumor) 


<br/>


Sumerian Morph Details
-----------------------------------------
MTAAC and CDLI Documentation - \
https://cdli-gh.github.io/guides/guide_tagsets.html

ETCSRI's Morphological Parsing - \
http://oracc.museum.upenn.edu/etcsri/parsing/index.html


Morphological Chart - \
https://docs.google.com/spreadsheets/d/1y0_y9HDQNwH0VqDCjjYuUpFsugw4GEybu6Pu01I_D9c/edit#gid=0

Tag Translations - \
[data/Morph_info_and_samples/tag-translation.tsv](data/Morph_info_and_samples/tag-translation.tsv)


<br/>



Compiling
-------------------------------------------------------------
-------------

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
-----------------------------------------------------------------------
--------

If you are in the source directory after running make, the following
commands should work:

```console
$ echo "pisan-dub-ba nig2-ka9-ak ab-ba-mu giri3 a-tu" | apertium -d . sux-eng
Basket-of-tablets account of Abbamu and under the authority of Atu
```
To translate the whole file -
```console
$ cat test/sux-eng-input.txt | apertium -d . sux-eng
Basket-of-tablets account of Abbamu and under the authority of Atu
```

After adding `/path/of/apertium-sux-eng` in your `$PATH` variable, you should be able to run it from anywhere, e.g. -

```console
$ echo "mu {d}szu-{d}suen lugal uri5{ki}-ma-ke4 ma2-dara3-abzu {d}en-ki-ka bi2-in-du8" | apertium sux-eng
year Szusuen king of Urim caulked Madaraabzu of Enkik
```
<br/>



Rule Based Engine 
--------------------
--------


## Nouns 

Noun tag converted into phrase using 4 major components
1. demonstrative_proposition - use of this that, it supposed to be at start
2. connecting_pronouns - pronouns like ("i am", "you are" etc.)
3. pre_noun_preposition - the prepositions which needs to there before the root noun or the possive possive_pronouns (to, for, with etc)
4. possive_pronouns - pronouns like (his,him). 

```
NP -> %n { 
      1(demonstrative_proposition) 1(connecting_pronouns) 1(pre_noun_preposition) 1(possive_pronouns)  _ 1 
      };
```

<br/>

## Numbers
Number can have case endings and morphologies similar to noun so are handeled same as noun 
```
NU -> %num { 1(demonstrative_proposition) 1(connecting_pronouns) 1(pre_noun_preposition) 1(possive_pronouns)  _ 1 };
```
**NOTE** - Numbers pipeline can be added seperately once developed 

<br/>

## Named Entities 
proper nouns/ Named Entities can have case endings and morphologies similar to noun so are handeled same as noun \
In addition some Rules from -  https://github.com/cdli-gh/cfg-parser/blob/master/parse_comm.cfg

1. mu PN-sze3 := "mu" Person "-sze3" (AGENT -> MU PERSON) \
person in whose name the receiver or supplier acted - interpretation: mu "name" + PN[.GEN].TERM (terminative indicates goal) \
i.e. "for the name of PERSON" \
note: we do not check the terminative case here! 

2. PN.maszkim := Person "maszkim" (AGENT -> PERSON MASZKIM)
overseer of the transaction
interpretation: maszkim "administrator" + PN.ABS, i.e., nmod (epithet) of PN.ABS

3. "from PERSON"
AGENT -> KI PERSON
ki ab-ba-sa6-ga-ta "from Abbasaga" (P102335), but also ki ab-ba-sa6-ga (P106228, without case marking)

4. mu-DU.PN := "mu-DU" Person
 person on whose account the transaction took place.
interpretation: mu-kux(DU) "delivery" + PN.GEN (on account of PN), if it's a god, it means "of the temple of X" where X is **dn**

```
PR_NM ->  mu@n %np.*.pn {
            (
                  if (2.lem/sl EndsWith sze3)
                  [for@det _ the@det _ name@n _ of@cnjadv _ 2]
                  else
                  [1(demonstrative_proposition) 1(connecting_pronouns) 1(pre_noun_preposition) 1(possive_pronouns)  _ 1]
            )
      } |
      %np.*.pn maszkim@n{ 
            administrator@n _ 1
      } |
      ki@n %np.*.pn{ 
            from@cnjadv _ 2
      } |
      giri3@n %np.*.pn{ 
            under@cnjadv _ the@det _ authority@n _ of@cnjadv _ 2
      } |
      mu-DU@n %np.*.pn{ 
            on@cnjadv _ the@det _ account@n _ of@cnjadv _ 2
      } |
      mu-DU@n %np.*.dn{ 
            of@cnjadv _ the@det _ temple@n _ of@cnjadv _ 2
      } |
      %np {1(demonstrative_proposition) 1(connecting_pronouns) 1(pre_noun_preposition) 1(possive_pronouns)  _ 1 };
```

<br/>

## Combining Named Entities, Numbers and Nouns
1. when nouns or named entities appears with genative then combine them into single phrase (ex - king of Ur)
2. any named enitites appears together connect tham with "and" (ex.(personal name) - ur-namma and ur-diri)
3. otherwise keep noun or named entitiy as it is
4. if we have non finite verb it acts as an adjective so verb before noun phrase (adj, Noun)

```

combined_PN_NP_NU -> 
                  %NP %NP.*.gen {
                       1 _ 2
                  } |
                  %NP %PR_NM.*.gen {
                       1 _ 2
                  } |
                  %PR_NM %PR_NM.*.gen {
                       1 _ 2
                  } |
                  %PR_NM.*.[names] %PR_NM.*.[names] {
                        1 _ and@cnjadv _ 2
                  } |
                  %NP %NU { 
                        2 _ 1 
                  } |
                  %NP %vblex.*.nf { 
                        2 _ 1 
                  } |
                  %PR_NM %vblex.*.nf { 
                        2 _ 1 
                  } |
                  %PR_NM {
                        1
                  } | 
                  %NP {
                        1
                  };
```

<br/>

## Verbs
1. if we get verb followed by erg and abs (erg,abs,verb) then erg word act as subject, then verb, and abs word act as object (SVO English reordering)
2. if we get verb followed by abs and erg (erg,abs,verb) then again erg word act as subject along with prsubject prepositions of erg word (like this that), 
then verb, and abs word act as object (SVO English reordering)
3. If we already have a subjective pronoun in a verb and is followed by an abs then we place (S,V from verb) and noun phrase as object (O) so (SVO). 
4. else, noun phrase acts as a subject, so we replace subject position with noun phrase in verb writing (SVO) 

```
VP -> %combined_PN_NP_NU.*.erg %combined_PN_NP_NU.*.abs %vblex {
            1(pre_subj_preposition)  1 1(post_subj_preposition) _ 3 _ 1(mid_prn) 1(pre_obj_preposition) 2
      } |
      %combined_PN_NP_NU.*.abs %combined_PN_NP_NU.*.erg %vblex {
            1(pre_subj_preposition)  2 1(post_subj_preposition) _ 3 _ 1(mid_prn) 1(pre_obj_preposition) 1
      } |
      %combined_PN_NP_NU %vblex {
            (
            if ( ( (2.subj_prn not = "") and (1.n5_2 = abs) ) )
                  [2(pre_subj_preposition)  2(subj_pronoun)  2(post_subj_preposition)  2 _ 1 _ ]
            else
                  [2(pre_subj_preposition)  _ 1 _ 2(post_subj_preposition)  2 _ 2(mid_prn) 2(pre_obj_preposition) 2(obj_pronoun)]
            )
      } |
      %vblex {
            1(pre_subj_preposition)  1(subj_pronoun) 1(post_subj_preposition)  1 _ 1(mid_prn) 1(pre_obj_preposition) 1(obj_pronoun) 
      }; 
```

<br/>


NMT and Rule Based Comparision
--------------------
--------


For the comparision I am using the **dev** data from the [mtaac_syntax_corpus](https://github.com/cdli-gh/mtaac_syntax_corpus) 

For comparing and testing on a new data checkout - [**sux_apertium_test.ipynb**](Notebooks/sux_apertium_test.ipynb) 

For neural netowrk (NMT) the previously developed best translation was used. For more details refer - https://github.com/cdli-gh/Semi-Supervised-NMT-for-Sumerian-English

To use the current mentioned pipleine download weights using
```
wget https://cdlisumerianunmt.s3.us-east-2.amazonaws.com/BackTranslation/<shard_num>st/_step_10000.pt
```
and change the location of weight path in [**sux_apertium_test.ipynb**](Notebooks/sux_apertium_test.ipynb) \
weight_location = '../../Data/_step_10000.pt' \
to \
weight_location = your/downloaded/weight/path

**Note** - To run the model for a sentences or the whole file use [**sux_apertium_test.ipynb**](Notebooks/sux_apertium_test.ipynb)
<br/>

## Evaluation

The evaluation is done using the BLEU metric on the dev set as mentioned above - 


| Machine Translation System  | Mean  | Median |
|---|---|---|
| **rule based**     | 19.156  |  20.4517 |
|  **neural network** |  18.868 | 6.881  |

*The **mean** and **median** scores for both Rule Based and NMT Engine* \
*with weightage of (0.75,0.25,0,0) over n-grams*

<br/>

**Note** -  As it can be observed from the bleu scores, the mean scores are almost similar for both Rule based and NMT, but the median score is pretty high for the Rule based engine, which indicates that the overall translation performance for each sentence is somewhat good for rule based engine with respect to NMT which is performing very good for some of the sentences and quite low for the remaining sentences.
<br>


Files and data
---------------------------------------------------------------------
--------


* [`apertium-sux-eng.sux-eng.dix`](apertium-sux-eng.sux-eng.dix) - Bilingual dictionary
* [`apertium-sux-eng.sux-eng.rtx`](apertium-sux-eng.sux-eng.rtx) - Structural transfer rules for translating into English
* [`apertium-basics`](Docs/Apertium-non-recursive/) - Apertium Basics (Docs)
* [`sumerian-language`](Docs/Sumerian/) - Sumerian Langauge understanding (Docs)



Adding data
---------------------------------------------------------------------
--------
The data can be added to the dictionaries by adding it in **.conll** file format and running the [sux_dict_prepration.ipynb](Notebooks/sux_dict_prepration.ipynb) file. You also need to clone it --- compile it ( use make ) and then compile  `apertium-sux-eng`. 



For more information
------------------------------------------------------------------
--------

* https://wiki.apertium.org/wiki/Installation
* https://wiki.apertium.org/wiki/Apertium-recursive/Formalism

<br />

Credits :
------------------------
-------

Himanshu Choudhary (Developer) \
Christian Chiarcos, (Mentor) \
Émilie Pagé-Perron, (Mentor) \
Rachit Bansal (Mentor)



<!-- 
Help and support
-------------------------------------------------------------------------------

If you need help using this language pair or data, you can contact:

* Mailing list: apertium-stuff@lists.sourceforge.net
* IRC: `#apertium` on irc.oftc.net (irc://irc.oftc.net/#apertium)

See also the file [`AUTHORS`](AUTHORS), included in this distribution. -->
