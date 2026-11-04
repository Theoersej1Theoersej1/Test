# Coding task – sample 1 (Asger)

| Fil | Indhold |
|---|---|
| `Task1_sample1_Asger_extraction.xlsx` | **Task I**: 47 disloyalitets-events fra de 25 artikler (Actor / Action / Date / Location / Confidence, ordret) + ark med 23 fravalgte kandidater og deres begrundelse + konventioner |
| `Task2_sample1_Asger_coded.xlsx` | **Task II**: de 50 events kodet med de 32 action-koder. Kolonnerne A–D er uændrede. Nye kolonner: `codes`, `code_labels`, `secondary_codes_for_review`, ordret `evidence`, `justification` og `flags`. Derudover arket `code_matrix` (0/1 pr. kode) og `code_key` (kodeliste og fordeling) |

## Metode og kvalitetssikring
- **Ordret gengivelse:** Alle citatfelter i Task I består udelukkende af ordret kildetekst. Flere passager er adskilt med ` // `, som i jeres egen Task II-fil. Hvert eneste segment er maskinelt tjekket mod artikelteksten med 0 afvigelser. Kildens skrivemåde (`SOLDIERs`, `protesters ,`) er bevaret, men PDF'ens orddelingsbindestreger ved linjeskift er fjernet.
- Alle belægscitater i Task II er tilsvarende tjekket ordret mod `action_description` i regnearket med 0 afvigelser.
- **Én række pr. aktørgruppe og pr. hændelse:** Militær og politi i samme sætning giver to rækker (artikel 7). Forskellige byer eller dage giver separate rækker (fx artikel 17 og 21).
- **Ingen inferens:** Felter står tomme, hvor artiklen ikke selv angiver dato eller sted. Der er ingen beregnede datoer og ingen kampagnelokationer.
- **Task II:** Kolonnen `codes` er svaret, dvs. de koder beskrivelsen direkte understøtter. Kolonnen `secondary_codes_for_review` er *ikke* en del af svaret. Den viser forsvarlige alternativer, så en reviewer kan tage stilling.

## Fund der bør reviewes (markeret med gult i `flags`)
1. **Datokonflikter:** Art. 3 siger "Saturday [16 April]", men 16. april 2006 var en søndag. Art. 12 angiver "30 September", men begivenheden var 30. november. Art. 7 har dateline 23. nov., mens kildelinjen siger 22. nov. 2155 GMT.
2. **Kildetekst med fejl:** Art. 17: "promising to clash with the people" har tydeligvis mistet et "not" ved tekstkonverteringen (jf. "won be used"). Teksten er kopieret ordret og markeret.
3. **Aktørens berettigelse:** Henri Cesar Sama (art. 23) har her kun en regeringstitel. Art. 21 viser, at han er NAVY LIEUTENANT. Retirerede generaler, der handler politisk (Task II row 278, 1872), og Zakharchenko (row 899), der er indenrigsminister i den siddende regering, er også markeret.
4. **Hvem er den siddende magt (incumbent):** I Elfenbenskysten 2011 (art. 10) er det uklart, om det er Gbagbo eller Ouattara. Der er kodet i forhold til Gbagbo som de facto-magthaver.
5. **Ren non-intervention:** Hændelser, hvor sikkerhedsstyrker kun ser til (fx art. 6, 18 og 25), er medtaget, fordi appendix type 2 eksplicit omfatter dem. De er dog markeret BORDERLINE, fordi illoyaliteten er svag.
6. **Historiske hændelser:** Bolivias politimytteri i feb. 2003 (art. 9) og Elfenbenskystens kup i dec. 1999 (art. 20 og Task II row 1486) er medtaget som BACKGROUND-EVENT.
7. **Andre aktører i beskrivelsen:** Nogle Task II-beskrivelser indeholder handlinger fra andre aktører end den angivne, fx State Security-generalerne i row 173 og de rebelske junior officers i row 1583. De er ikke kodet på eventet, men nævnt i `flags`.
