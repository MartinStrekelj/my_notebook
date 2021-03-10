# 1. Kodiranje

:::note
Kodiranje se je pojavlo precej daleč nazaj. Kodiranje podatkov v drugo abecedo. Razlog je bil, da je bil prenosni medij drugačen od običanjega komunikacijskega medija (ko govorimo pišemo na papir, da to ohranmo).
:::

Prva potreba po kodiranju je telegraf. Kodiranje govora v enostavne znake -> pojav morzejeve besede. Vse ideje dobrega kodiranja predstavljajo osnovo za stiskanje podatkov, šifriranje in prenos po kanalu.

**Prvi Shannonov teorem** -> temelji za dobro kodiranje.

Smiselno bolj verjetne znake na manjši zapis. Več znakov v blokih je bolje, kot če kodiramo vsak znak posebaj. Omejili se bomo na to, da opazujemo dogodek in hočemo opisati dogodek.

![kodiranje](/img/TIS/2/Rokopis_2021-03-01_1.jpg)

**_Kod je preslikava iz osnovne abecede v kodirno abecedo._**

Zgodovinsko pomemben je **morsejev** kod.

- E -> .
- T -> -
- A -> .-
- S -> ...
- O -> ---
- SOS -> ... --- ...

Potem **ASCII**

- A -> 1000001
- B -> 1000010
- ...

## 1.1. Razvrstitev kodov

![razvrstitevKodov](/img/TIS/2/Rokopis_2021-03-01_2.jpg)

:::note

- **_singularen_**, en znak je ena kodna zamenjava / unikatna kodna zamenjava

- **_enoznačen_** pomeni, da vemo kje se začne novi in konča prejšna kodna zamenjava

- **_trenutni_** je, da ko dobimo zadnji znak že vemo, da je to zadnji znak

  - **!!!** Kod je trenutni, ko nobena kodna zamenjava **ni** predpona drugi kodni zamenjavi.

- **_enakomerni_** vse kodne zamenjave imajo enako število znakov

**_Bolj pomembno nam je, da je povprečna dolžina kodne zamenjave manjša kot, da je enakomerno._**

:::

Kode lahko zapisujemo tudi v obliki kodnih dreves.

![kodnaDrevesa](/img/TIS/2/Potrdilo_2021-03-01_3.jpg)

## 1.2. Kraftova neenakost

:::note

- **_Je test, ki nam pove, če obstaja trenutni kod z danimi dolžinami kodnih zamenjav._**

:::

![KraftovaNeenakost](/img/TIS/2/Rokopis_2021-03-01_4.jpg)

## 1.3. Shannonov teorem

:::note

- Večji kot je m, večja tudi zakasnitev kodiranja in dekodiranja
- Večji kot je m, bližje smo entropiji (optimalni kod)

:::

![shannon1](/img/TIS/2/Rokopis_2021-03-01_6.jpg)
![shannon2](/img/TIS/2/Rokopis_2021-03-01_7.jpg)

**_Več znakov kot uzamemo, boljša je kodna zamenjava. Plačamo z kompleksnostjo kodne zamenjave._**

## 1.4. Stiskanje

Vsakodnevno stiskanje. Npr zippanje (brez izgubno stiskanje), slike v stisnjenih formatov (JPEG - izguba pri stiskanju), video/audio stiskanje
Stiskanje je bolj kompleksno kot odpakiranje stisnjenega formata.
Množica tehnik za stiskanje.

## 1.5. Shannonov kod

Algoritem - ni ravno najboljši / teoretični (Različna poimenovanja)

Enostavno bomo šli čez, pogledali ga bomo kot algoritem

:::note

- Znake razvrstimo po padajočih verjetnostih
  - Cilj je dobiti različne kodne zamenjave
- Določimo število znakov v kodni zamenjavi -> Lk = ^ -log r Pk ^
- Izračunamo komulativne verjetnosti
- Kumulativne verjetnosti pretvorimo v bazo r -> Kodna zamenjava je prvih l,k znakov necelega dela pretvorbe

:::

![shannonovKod](/img/TIS/2/Rokopis_2021-03-02_8.jpg)

## 1.6. Fanojev kod

:::note

- Znake razporedimo po padajočih verjetnostih
- Znake razvrstimo v r čim bolj enakih skupin (enakost je vsota verjetnosti znakov)
- Vsaki skupini priredimo en znak kodne abecede
- Postopek ponovimo na vsaki skupini posebaj

:::

![fanojevKod](/img/TIS/2/Potrdilo_2021-03-02_9.jpg)

## 1.7. Kviz

![kviz2](/img/TIS/2/kviz2.png)

![kviz naloga 4](/img/TIS/2/kviz4.jpg)

![kviz naloga 5](/img/TIS/2/kviz5.jpg)
