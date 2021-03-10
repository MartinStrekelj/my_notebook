
# 1. Uvodni primer

Imamo podatke o študentih, ki so izbirali predmete.

Sx -> množica vseh študentov, ki so izbrali predmet x

Podobnost med predmetoma I in J

![formula1](/img/PR/1/formula1.jpg)

števec je presek || imenovlec je unija
Delež študentov, ki so izbrali oba predmeta, med vsemi študenti, ki so izbrali vsaj enega od dveh predmetov

Delež je med 0 in 100% (0 <= x =< 100)

Pri PR namesto podobnosti merimo razdaljo.

Različnost med predmeti je obrnjena podobnost

![formula2](/img/PR/1/formula2.jpg)

Izračunamo razdalje za vse možne pare -> dobimo tabelco

Manjša številka => Večja podobnost

Prikaz na drug način => HeatMap

![heatmap](/img/PR/1/heatmap.jpg)

Boljši način prikaza => 2D prikaz => vsako vozlišče je en predmet => bližje sta predmeta manjša je razdalja => **_MDS -> multidimensional scalling_**

![2d](/img/PR/1/2d.jpg)

**_Dendrogram_** -> dobimo z gručenjem (razvrčanje v skupine) -> odločimo kje potegnemo črto, da dobimo skupine

![dendogram](/img/PR/1/dendogram.jpg)

S vizualizacijo smo nekaj odkrili vendar, ne vsega.

Dve težavi:

- Vsebuje le izbor predmetov, ki jih študenti poslušajo eno leto
- Mera podrobnosti (npr Ang se 3x ponovi,...)

Glavna težava? -> ne vemo kaj je sploh namen analize

## 1.1. Primer uporabe

Naredimo **Svetovalni sistem** -> študenti, ki so izbrali A so izbrali tudi B...

Študent je izbral k predmetov: s1, s2,... sk

![bayes](/img/PR/1/formulabayes.jpg)

Limitiramo le na prvih pet najbolj verjetnih.

Iz tega lahko naredimo preprosto aplikacijo.

Naredimo **Podobnost med študenti**
-> dva študenta sta podobna, če izbirata podobne predmete.

## 1.2. Kaj je podatkovno rudarjenje

- data mining
- data science
- odkrivanje zakonitosti podatkov

Cilj je iskanije **_vzorcev v podatkih_**, ki so uporabni. Te želimo uporabiti nato pri odločanju, razumevanju,...

**_Poudarek na praktičnosti_** in ne toliko na matematični rigoroznosti:

- Domiselna uporaba podatkov
- Domiselna vizualizacija
- Domiselna izbira metod statistike, strojnega učenja, ...

### 1.2.1. Primeri uporabe

Praktično povsod.. npr:

- Poslovna inteligenca
- Sistemi za odnose s strankami
- Analiza kupovalne košarice
- Odkrivanje zlorab (banke, ponudniki kreditnih kartic)
- Družbeno-ekonomske analize
- Analiza prostorskih podatkov
- Znanost in tehnika
  - Genetika
  - Farmacija
  - Astronomija
  - Medicina

## 1.3. Metode

:::note
**!!!**

- Podatki in problemi (poznavanje domene podatkov, človeški faktor)
- Vizualizacija (predstava podatkov)
- Modeliranje (abstrakcija)
- Vrednotenje modelov (ali je model dober, natančnost modela)
- Uporaba rezultatov
:::

**Včasih pogled na metode linearen (enosmeren), danes vse poteka bolj ciklično.**

### 1.3.1. CRISP-DM

**_Postavil IBM_**

![crispdm](/img/PR/1/crispdm.jpg)

### 1.3.2. SEMMA

**_Postavil SAS Institute_**

Linearen, zaporedje korakov
Logična izbira za prodajanje software za analizo podatkov.

![semma](/img/PR/1/semma.jpg)

### 1.3.3. Podatki in problemi

1. Naročnik želi, da **_podatki analiziramo_**
    - ni očitno kaj z njimi narediti
    - vprašanje kaj želimo doseči z analizo

2. **_Spoznavanje področja, konkretnega problema in podatkov na razpolago_**.
   - Kako so podatki zbrani?
   - Kakšen je pomen posameznega podatka?
   - Kakšne so običajne vrednosti?
   - Distribucije vrednosti, osamljene primere?
...

3. **_Podatke obdelamo - abstrakcija_**

4. **_Vizualizacija_**
     - Izris ponavadi/pogosto zadošča za analizo: -> pametne slike
     - Diagrami, zemljevidi, grafi, histogrami, razsevni diagrami, mozaični (parketni) diagrami,...

### 1.3.4. Modeliranje

Če slika ni dovolj za analizo naredimo modele.

:::note

- **_Model_** => klasifikator ali regresor
- **_Model_** pove kako iz začetne vrednosti X dobimo Y
- poudarek na **_matematično preprostih modelih_**
  - Bayesov klasifikator
  - drevesa
  - povezovalna pravila
  - linearna regresija
- **_Izogibamo se black box_** -> črne škatle ne povejo kako iz X dobimo Y -> ne razumemo
- Razvrščanje v skupine (gručenje) - je neke vrste model ampak ne vemo kaj je lastnost, ki loči eno gručo od druge

:::

### 1.3.5. Vrednotenje modelov

Če vrednotimo model, ga moramo vrednotiti na **testnih** podatkih -> podatki, ki jih model med učenjem ni videl

Dve dimenziji rangiranja

- Kolikšen delež vrednotenih je pravilen
- Kako dobro modeli ločijo med razredi

### 1.3.6. Uporaba modela

- poročilo o analizi in modeliranju
- uporaba modela v aplikaciji

## 1.4. Podatki

Kakšne podatke poznamo?

- **_nestrukturirani_** (slike, datoteke)
- **_strukturirane_** (v podatkovnih zbirkah,..)

- besedila
- ocene filmov
- gibanje delnic
- trgovinski računi
- EKG posnetki
- ...

Podatke moramo spraviti v ustrezno obliko

- **_Tabelarični_**

![TabelaricniPodatki](/img/PR/1/tabelaricniPodatki.jpg 'Tabelaricni podatki')

- **_Relacije med pari objektov_** (npr, socialna omrežja)

![RelacijeMedPodatki](/img/PR/1/relacijeMedPodatki.jpg)

### 1.4.1. Tabelarični podatkiv - pretvorba v 'standardno' obliko

primer -> spam pošta -> obkljukamo (0/1) ali je spam nato se sistem nauči in sam ve kaj je spam

Včasih je problem čas -> čas je pomembna komponenta, ki pa jo je težko modelirati

#### 1.4.1.1. Preverjanje pravilnosti podatkov

- Običajni obsegi vrednosti, možna odstopanje?
- Očitno napačni (deli) podatkov?
  - noseči Angleži
- Konsistentnost? (enake merske enote)
- Uporabni za modeliranje? So vsi podatki dosegljivi v času uporabe modela
  - katere podatke bomo zares imeli, ko ga bomo uporabljali
- Povezave med atributi, ki se jih moramo znebiti
- Korelacija med podatki
- Redundatni podatki
- Interakcije med atributi
  - XOR primer - iz vrednosti enega atributa ne moremo napovedati funkcije
- Atribut z veliko napakami
  - zvezne diskretiramo, pretvorimo v intervale
- v celoti izpustimo, raje kot da nas napačna vrednost zavede
- Združimo z atributi s podobni pomenom, ki so prav tako nezanesljivi
- Atribut z manjkajočimi vrednostimi
  - uporabimo metode, ki znajo takšne ignorirati (naivni bayes)
  - če veliko manjka, izpustimo
  - uganemo manjkajoče vrednosti
  - napovemo vrednost iz drugih atributov
  - vstavimo najpogostejšo ali povprečno vrednost

!["Kviz1"](/img/PR/1/kviz1.png "Kviz1")
