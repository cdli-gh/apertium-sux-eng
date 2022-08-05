# examples with source, annotation and gold translation

## lexicon

	ag (ag2) V "measure"
	ak V "do"
	ba V "allot"
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

- `NEG` "not"

	nu-du3-am	<NEG><V><3-SG-S><SUB><COP-3-SG>
	"it is not built (=du3)" (P432264)

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

	analoguously: `1-SG`, `2-SG`, `1-PL`

- dimensional prefixes (= the things in a verbal tag that look like case labels)

	> note: if a clause contains an argument with the same case, then these should not be generated from the verb)

	> note: the first dimensional prefix will take the IPP pronoun, if there are multiple IPP pronouns, we do not know which pronominal form they take, it's probably best to translate the first dimensional prefix only and to ignore the others

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

		(two places are named but annotation says singular, so "was")

	> Note if `SUB` occurs with an *English* adjective, ignore it, for a verb meaning "(being) blue", the literal translation would be "that what is blue", but we just keep "blue"

		lugal	<N>
		kal-ga	<NF><V><SUB>

		"strong (=kalag) king(=lugal)" (P430412)
		NOT "king who is strong"


do not translate (no CDLI examples with translation found)
- `MOD1` "it is possible that" (with present tense), "it is certain that" (with past tense)
- `ANT` "after"
- `RDP` (reduplication, could mean "much" or "many" or "all")
- `MOD2` "it is my (our) intention to ..."
- `MOD3` "do not" or "may he not"
- `MOD5` "not"
- `MOD6` "?"
- `MOD7` "certainly"
- `FIN-LI` (`FIN-L1`)
- `FIN-L2`
- `COOR` "and" (between last and current clause)
- `VEN` "towards" (no example with literal translation found)
- `LOC-OB` is unclear (yet another locative, not in our data)

## nouns (N,PN, ...N)

## nominalized verbs (NV, NU)