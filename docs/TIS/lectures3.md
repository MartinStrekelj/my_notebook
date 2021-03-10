# 1. Huffmanov kod

Fanoj je predaval na MIT. Huffman je pri njemu opravil seminar, ki je dalo optimalno rešitev. Predstavlja osnovo za večino stiskalnih algoritmov.

Združujmo posamezne znake v sestavljen znak in nato delamo samo še z sestavljenim znakom.

:::note

**_Imamo dve fazi_**

- **_Združevanje_**
  - Ciljna abeceda ima r znakov
  - Poišči r najmanj verjetnih znakov
  - Te znake združimo v fiktivni sestavljeni znak
  - Njegova verjetnost je vsota vseh verjetnosti r najmanj verjetnih znakov
  - Postopek ponovimo s sestavljenim znakom
  - Ponavljamo, dokler nam ne ostane 'r' znakov -> na ta način zgradimo drevo
- **_Razdruževanje_**
  - Vsakemu preostalemu znaku priredimo en znak kodne abecede
  - Vsak sestavljeni znak razstavimo in mu priredimo en znak kodne abecede
  - Zaključimo, ko ni več sestavljenih znakov

:::

Zvezek1

:::note

**_Huffmanov kod je optimalen_**:

- Ni neizrabljenih vej
- Najdaljše kodne zamenjave so v parih
- Najdaljše kodne zamenjave ustrezajo najmanj verjetnim znakom
- Če dva najmanj verjetna znaka nadomestimo s sestavljenim znakom se L zmanjša
- L < 1 za dva znaka ni mogoč

:::

Zvezek2

Lastnosti Huffmanovega koda:

Zvezek3

## 1.1. Aritmetični kod

Zamisel pri IBM (Razlog patenti v 80. letih). JPEG na začetku kodiran s Huffmanom potem pa, ko je patent padel so uporabili Aritmetični kod.

:::note
Opis algoritma:

- Znakov ne razvrščamo
- Začnemo na intervalu 0 - 1
- interval razdelimo na n podintervalov, pri tem se ti podintervali ne prekrivajo. Širine podintervalov ustrezajo verjetnosti. Bolj verjeten znak bo imel širši podinterval.
- Izberemo podinterval, ki predstavlja naš znak.
- Podinterval razbijemo na podintervale
- Če niz še ni končan ponovno razbijemo na intevale in se vrnemo na 3. korak -> dobimo vse ožje znake
- Niz znakov predstavimo s podintervalom

:::

Zvezek4
