
# examples with source, annotation and gold translation

## lexicon

	ag (ag2) V "measure"
	ak V "do"
	ba V "allot"
	dim V "create", "fashion"
	du (du3) V "build"
	dug V "speak" (also "swear")
	e (e3) V "leave" (also "remove", if with `ABL`)
	gal (gal2) V "be" (= "exist")
	hug V "hire"
	hulu V "destroy"
	sa V "pay for" (also "give (in exchange) for")
	ur3 V "erase" (lit. "level off")

	lugal N "king"
	mu N "year"

	kalag V "(be) strong" => adjective

## verb (V)

- `MOD4` "certainly"

		ba-ra-ba-ta-e3	<MOD4><MID><ABL><V><3-SG-S>
		"he did (certainly) not let him leave (=e3)" (P465383)

- `MID` translate as passive clause

		ba-hun  <MID><V><3-SG-S> 
		"he was hired (=hug)" (P370955)

- initial pronominal prefixes ("IPP", V5/V6), must be before dimensional prefixes (i.e., those things that look like case labels)
	
	- `3-NH` "[prep +] it", e.g., `<3-NH><TERM>` "against it"

			ib2-szi-ag2-ge26-a <FIN><3-NH><TERM><V><3-SG-A><SUB>
			"that he shall measure (=ag2) against it" (P465383)

	- `3-SG-H` "[prep +] him", e.g., `<3-SG-H><DAT>` "for him"

			in-na-ba <FIN><3-SG-H><DAT><3-SG-H-A><V><3-SG-P> 
			"he allotted (=ba) it for (to) him" (P458780)

	- `3-PL` "[prep +] them", e.g., `<3-PL><DAT>` "for them"

			mu-ne-du3  <VEN><3-PL><DAT><3-SG-H-A><V><3-SG-P>
			"he built (=du3) it for them" (P332420)

	- analoguously: `1-SG`, `2-SG`, `1-PL`

- dimensional prefixes (= the things in a verbal tag that look like case labels)

	> note: if a clause contains an argument with the same case, then these should not be generated from the verb)

	> note: the first dimensional prefix will take the IPP pronoun, if there are multiple IPP pronouns, we do not know which pronominal form they take, it's probably best to translate the first dimensional prefix only and to ignore the others.

	- `DAT` "for [+ IPP pron]", e.g., `<3-PL><DAT>` "for them"

			mu-ne-du3  <VEN><3-PL><DAT><3-SG-H-A><V><3-SG-P>
			"he built (=du3) it for them" (P332420)

	- `COM` "with [+ IPP pron]", e.g., `<3-SG-H><COM>` "with him"

			in-da-gal2      <FIN><3-SG-H><COM><V><3-SG-S>
			"with (against) him, it exists (=gal)" (P129708)

	- `ABL` "from [+ IPP pron]", e.g., `<3-NH><ABL>` "from there" (there ~ it)

			ub-ta-e3        _<ANT><3-NH><ABL><3-SG-H-A><V><3-SG-P>
			"after he has left (=e3, here "remove") it from there" (P432347)

	- `TERM` "to/towards [+ IPP pronoun]", e.g., `<3-SG-H><TERM>` "to him"
		
			in-szi-sa10 <FIN><3-SG-H><TERM><3-SG-H-A><V><3-SG-P><SUB>
			"he pays (=sa) it to him " (P122929)

	- `L1` "in/into [+ IPP pronoun]", also "here" if without IPP pronoun or with inanimate IPP pronoun
	
			i3-gal2 <FIN><L1><V><3-SG-S>
			"it is (=gal2) here" (P108044)

	- `L2` "on/to [+ IPP pronoun]", also "there" if without or with inanimate IPP pronoun, e.g., `<3-NH><L2>` "there"

			bi2-in-ak-bi	<3-NH><L2><3-SG-NH-P><V><3-SG-A><SUB>
			"that he had done (=ak) it there" (P432140)

	- `L3` "near/at/towards [+ IPP pronoun]", also "then" if without or with inanimate IPP pronoun, e.g., `<3-SG-NH><L3>` "then"

			bi2-in-du11     <3-SG-NH><L3><3-SG-H-A><V><3-SG-P> 
			"he spoke (=dug, here: swore) it then" (P103956)

	- `L1-SYN` like `L1`
	- `l2-SYN` like `L2`

- subject and object pronouns (before and/or after the verb)

	- `3-SG-H-P` (preverbally) "him" (as object)

			bi2-in-ur3  <3-NH><L2><3-SG-H-P><V><3-SG-A><SUB>
			"that he erases (= ur3) him there" (P432346)

	- `3-SG-NH-P` (preverbally) "it" (as object)
		
			bi2-in-ak-bi	<3-NH><L2><3-SG-NH-P><V><3-SG-A><SUB>
			"that he had done (=ak) it there" (P432140)

	- `3-SG-H-A` (preverbally) "he" (as subject)
		
			in-szi-sa10 <FIN><3-SG-H><TERM><3-SG-H-A><V><3-SG-P><SUB>
			"he pays (=sa) it to him " (P122929)
	
	- `3-SG-A` (postverbally) "he/she/it" (as subject)

			ib2-szi-ag2-ge26-a <FIN><3-NH><TERM><V><3-SG-A><SUB>
			"that he shall measure (=ag2) against it" (P465383)

	- `3-SG-P` (postverbally), "it/he/she" (if with `-A`, object, otherwise subject)

			in-szi-sa10 <FIN><3-SG-H><TERM><3-SG-H-A><V><3-SG-P><SUB>
			"he pays (=sa) it to him " (P122929)

	- `3-SG-S` (postverbally) "it/he/she" (subject)

			i3-gal2 <FIN><L1><V><3-SG-S>
			"it is (=gal2) here" (P108044)


	- other persons analoguously 

		-	 preverbal: `1-SG-A`, `2-SG-A`, `3-NH`, `3-PL-DAT`, `3-SG-H-A`, `3-SG-HN-P`, `3-SG-H-P`, `3-SG-NH`, `3-SG-NH-A`, `3-SG-NH-L3`, `3-SG-NH-P`
		- postverbal: `3-PL`, `3-PL-A`, `3-SG-A`, `3-SG-P`, `3-SG-S`
		- for other possible tags, see tag-translation.tsv and ETCSRI documentation

- `SUB` relative clause, can be translated as "that", "what", "who"


		ba-hul-a	<MID><V><3-SG-S><SUB>
		"that it was destroyed (=hulu)" (P212356)

	with context

		mu	<N>
		ur-bi2-lum{ki}	<GN>
		ki-masz{ki}	<SN><ABS>
		ba-hul-a	<MID><V><3-SG-S><SUB>
		"year that Urbilum and Kimash was destroyed" (P212356)

	(two places are named but annotation says singular, so "was"; example also shows that you should generate pronouns from dimensional prefixes only if the corresponding case is not expressed in a full phrase)

	> Note if `SUB` occurs with an *English* adjective, ignore it, for a verb meaning "(being) blue", the literal translation would be "that what is blue", but we just keep "blue"

		lugal	<N>
		kal-ga	<NF><V><SUB>

		"strong (=kalag) king(=lugal)" (P430412)
		NOT "king who is strong"

- `NEG` "not" (hard, hence last)

		nu-du3-am	<NEG><V><3-SG-S><SUB><COP-3-SG>
		"it is that that wasn't built (=du3)" (P432264)

	> Note: `<COP-3-SG>` comes from nominal annotation, as `SUB` turns a morphological verb (= a syntactic clause) into a morphological noun (= syntactic relative clause), translated as "it is (that)". The passive is because there is no intransitive "build" in English

	analoguously (no examples found):
	- `MOD3` "do not" or "may he not"
	- `MOD5` "not"




do not translate (no CDLI examples with translation found)
- `MOD1` "it is possible that" (with present tense), "it is certain that" (with past tense)
- `ANT` "after"
- `RDP` (reduplication, could mean "much" or "many" or "all")
- `MOD2` "it is my (our) intention to ..."
- `MOD6` "?"
- `MOD7` "certainly"
- `FIN-LI` (`FIN-L1`)
- `FIN-L2`
- `COOR` "and" (between last and current clause)
- `VEN` "towards" (no example with literal translation found)
- `LOC-OB` is unclear (yet another locative, not in our data)

	mu-na-dim2	mu-nn-a-dim[create][-ø]	V	VEN.3-SG-H.DAT.3-SG-H-A.V.3-SG-P
	"he (=3.SG-H-A) created it (=3-SG-P) for him (=3-SG-H.DAT)"


## nouns (N,PN, ...N) and nominalized verbs (NF.V ~ adjective; NU = numeral; .PT or .SUB marks nominalization)

translation for the individual cases is clear, right?

in the following examples, syntax has been

P480071 (admin subcorpus)

	s1.col1.1.1	{d}szu-{d}suen	Szusuen[1]	RN	_	_	_
	s1.col1.2.1	lugal	lugal[king]	N	_	_	_
	s1.col1.2.2	kal-ga	kalag[strong]-a	NF.V.PT	_	_	_
	s1.col1.3.1	lugal	lugal[king]	N	_	_	_
	s1.col1.3.2	uri5{ki}-ma	Urim[1]-ak	SN.GEN	_	_	_
	s1.col1.4.1	lugal	lugal[king]	N	_	_	_
	s1.col1.4.2	an-ub-da	anubda[quarter]	N	_	_	_
	s1.col1.4.3	limmu2-ba	limmu[four]-bi-ak[-ø]	NU.3-SG-NH-POSS.GEN.ABS	_	_	_

	(1) strong king: N or PN before NF.V.PT becomes "adjective noun"
		noun has no inflection
		adj can have inflection (for the noun)
	(2) king of Urim: N before PN in genitive becomes "noun of PN"
		PN in genitive can carry additional inflection (for the head noun)
	(3) four quarters: N before NU becomes "NU N", NU can carry additional inflection (here, GEN.ABS) for the head noun
	(4) king of the four quarters: N before noun (phrase) in genitive becomes "N of NP", here, we evaluate the GEN attribute of immu2-ba
	(5) X, Y: sequence of noun phrases X Y, only the last has case marking (optional): "X, Y" or "X, the Y"; eventual case marking of the last (here ABS) defines the case of the entire phrase
	(6) then, check whether it's an argument of a following verb

cf. P500941 (royal subcorpus)

	9	{d}szu-{d}suen	Szusuen[1]	RN	RN
	10	lugal	lugal[king]	N	N
	11	kal-ga	kalag[strong]-a	V	NF.V.SUB
	12	lugal	lugal[king]	N	N
	13	uri5{ki}-ma	Urim[1]-ak	SN	SN.GEN
	14	lugal	lugal[king]	N	N
	15	an	An[1][-ra]	N	N
	16	ub-da	_	N	N
	17	limmu2-ba-ka-sze3	_[quarters]	NU	NF.V.3-SG-NH-POSS.GEN.GEN.TERM

the example is exactly the same (except for the entire phrase being GEN.TERM rather than ABS), the annotation is slightly different because it comes from a different subcorpus. the treatment of an-ub-da is an error in the second example, should be as in first)

	"Szusuen, strong king, king of Urim, king of the four quarters"

P500941

	1	{d}szara2	Szara[1][-ak]	DN	DN
	2	nir-gal2	_[jewel]	N 	N
	3	an-na	An[1][-ak][-ak][sze]	PN	DN.GEN


	"Szara, jewel of An" (An either god or "heaven")

P500941
	4	dumu	dumu[child]	N	N
	5	ki-ag2	ki'ag[love][-ø]	V	NF.V

	"loved child" [I guiss this will be tough to disambiguate] (actually, "beloved")

P500941
	4	dumu	dumu[child]	N	N
	5	ki-ag2	ki'ag[love][-ø]	V	NF.V
	6	{d}inanna	Inanna[1][-ak]	DN	DN.GEN

	"loved child of Inanna" 

P500941

	1	{d}szara2	Szara[1][-ak]	DN	DN
	7	lugal-a-ni-ir	_[his.lord]	N	N.3-SG-H-POSS.DAT-H

	"for (=DAT-H) Szara, his lord"

P500941
	1	{d}szara2	Szara[1][-ak]	DN	DN
	2	nir-gal2	_[jewel]	N 	N
	3	an-na	An[1][-ak][-ak][sze]	PN	DN.GEN
	4	dumu	dumu[child]	N	N
	5	ki-ag2	ki'ag[love][-ø]	V	NF.V
	6	{d}inanna	Inanna[1][-ak]	DN	DN.GEN
	7	lugal-a-ni-ir	_[his.lord]	N	N.3-SG-H-POSS.DAT-H

	"for Szara, jewel of An, loved child of Inanna, his lord"

P500941
	8	nam-ti	namtil[life]	N	N
	9	{d}szu-{d}suen	Szusuen[1]	RN	RN
	10	lugal	lugal[king]	N	N
	11	kal-ga	kalag[strong]-a	V	NF.V.SUB
	12	lugal	lugal[king]	N	N
	13	uri5{ki}-ma	Urim[1]-ak	SN	SN.GEN
	14	lugal	lugal[king]	N	N
	15	an-ub-da	[quarters]	N	N
	16	limmu2-ba-ka-sze3	[four]-b-ak-ak-sze	NU	NF.V.3-SG-NH-POSS.GEN.GEN.TERM

	"for (=TERM) the life (=nam-ti) of (=2nd GEN in 16) Szusuen, strong king, king of Urim, king of (= first GEN in 16) the four quarters"

P500941
	17	ur-{d}...	_[1][-ra]	PN	PN
	18	aga3-us2	aga'us[soldier]	N	N
	19	lugal	lugal[king][-ak]	N	N.GEN
	20	dumu	dumu[child]	N	N
	21	ur-ab-ba-ke4	_[Ur-abba]	PN	PN.GEN.ERG

	"Ur-..., soldier of (=GEN, line 19) the king, son of (=GEN, line 21) Ur-Abba"

## "sentences"

P500941

	# consolidated/train/P500941.conll-# tr.en: For Szara jewel of heaven beloved child of Inanna his lord for life of Szu-Suen strong king king of Ur king of four quarters did Ur- royal soldier son of Ur-abba this fashion

	1	{d}szara2	Szara[1][-ak]	DN	DN
	2	nir-gal2	_[jewel]	N 	N
	3	an-na	An[1][-ak][-ak][sze]	PN	DN.GEN
	4	dumu	dumu[child]	N	N
	5	ki-ag2	ki'ag[love][-ø]	V	NF.V
	6	{d}inanna	Inanna[1][-ak]	DN	DN.GEN
	7	lugal-a-ni-ir	_[his.lord]	N	N.3-SG-H-POSS.DAT-H
	8	nam-ti	namtil[life]	N	N
	9	{d}szu-{d}suen	Szusuen[1]	RN	RN
	10	lugal	lugal[king]	N	N
	11	kal-ga	kalag[strong]-a	V	NF.V.SUB
	12	lugal	lugal[king]	N	N
	13	uri5{ki}-ma	Urim[1]-ak	SN	SN.GEN
	14	lugal	lugal[king]	N	N
	15	an-ub-da	[quarters]	N	N
	16	limmu2-ba-ka-sze3	[four]-b-ak-ak-sze	NU	NF.V.3-SG-NH-POSS.GEN.GEN.TERM
	17	ur-{d}...	_[1][-ra]	PN	PN
	18	aga3-us2	aga'us[soldier]	N	N
	19	lugal	lugal[king][-ak]	N	N.GEN
	20	dumu	dumu[child]	N	N
	21	ur-ab-ba-ke4	_[Ur-abba]	PN	PN.GEN.ERG
	22	mu-na-dim2	mu-nn-a-dim[create][-ø]	V	VEN.3-SG-H.DAT.3-SG-H-A.V.3-SG-P

	"For Szara, jewel of An, loved child of Inanna, his lord, Ur-..., soldier of the king, son of Ur-Abba, fashioned this for the life of Szusuen, strong king, king of Urim, king of the four quarters"

	or 

	"Ur-..., soldier of the king, son of Ur-Abba, fashioned this for Szara, jewel of An, loved child of Inanna, his lord, for the life of Szusuen, strong king, king of Urim, king of the four quarters"

	or

	"For the life of Szusuen, strong king, king of Urim, king of the four quarters, Ur-..., soldier of the king, son of Ur-Abba, fashioned this for Szara, jewel of An, loved child of Inanna, his lord"

	(word order doesn't matter, both TERM and DAT can be translated as "for", TERM also as "towards")

