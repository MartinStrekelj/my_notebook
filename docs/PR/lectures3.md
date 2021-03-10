# 1. Vizualizacija

## 1.1. Box plot

- Za prikaz zveznih spremenljivk
- Kažejo osnovne statistike:
  - povprečje
  - mediano, ...
- Poleg histogramov primerne za prikaz zveznih distribucij
- Lahko postavimo enega zraven drugega in primerjamo populacije, dele vzorca (moški, ženske)
- Hitro poiščemo čudne primere, napake v podatkih
- ...

![boxChart](/img/PR/3/boxplot.jpg)

## 1.2. Stolpični diagrami (bar chart)

- Primerni za prikaz diskretnih atributov (ordinalnih ali nominalnih)
- Uporabni tudi za zvezne, vendar jih prej diskretiziramo
  - Ordinalne uredimo naravno (mladi, srednji, stari) od leve proti desni, od zgoraj navzdol
  - Nominalne uredimo na nek smiselen način (abeceda ni nujno najboljši način)
  - Vrstni red stolpcev pomemben, odvisen od namena primerjave posameznih primerov. S kom želimo primerjati Egipčane? Z geografskimi (Libicij in Izraelci) ali abecednimi sosedi -> sosednjimi
- Postavitev horizontalna je lažja za branje

![barChart](/img/PR/3/stackedBarChart.jpg)

### 1.2.1. Skala lahko zavaja

- Skala naj se vedno začne pri vrednosti 0, sicer popačimo vizualizacijo
- Gre za R&D res dvakrat manj denarja kot za prodajo?? (slika)

![skala](/img/PR/3/skala.jpg)

## 1.3. Histogrami

- Kadar količine (deleže ali števila nečesa) kažemo v vsakem stolpcu posebej (ne v obliki štrudlov)
- Kadar kažemo distribucije, jim rečemo histogrami.
- Vizualizacija na levi je zgrešena, ker dodana slika na desni navidezno poviše stolpec, čeprav je pol manjši od srednjega
- Izogibanje dodatnih okraskov pri vizualizaciji

### 1.3.1. Kaj je narobe?

![narobeViz](/img/PR/3/narobeViz.jpg)

- Slaba izbira barv
- Preveč informacij -> preveč vsega

Boljše:

![dobraViz](/img/PR/3/dobraViz.jpg)

- Baseline glede na razmerje prodaje
- Vidimo dinamiko skozi čas
- Zadnji stolpec (rdeč) predstavlja povprečje stolpcev

### 1.3.2. Po kategorijah

![kategorije](/img/PR/3/poKategorijah.jpg)

- Naštevanje ni po abecednem vrstnem redu, ampak po deležu

**_Dve kategoriji_**

![dveKategoriji](/img/PR/3/dveKategoriji.jpg)

- Omogoča lepo primerjavo po trgih
- Chamomile -> kamilice :D

### 1.3.3. Pozitivni in negativni odkloni

:::note

- **Barve pozitivno zeleno - negativno rdeče**
- **2D > 3D**
- **Čas od leve proti desni**

:::

![odkloni](/img/PR/3/odkloni.jpg)

### 1.3.4. Krivulje

- Lahko bi dodali še tabelo spodaj

![krivulje](/img/PR/3/krivulje.jpg)

- Nikoli ne kažemo neurejenih atributov
- Npr. mladoletnik -> moški -> ženske ???

![krivulje2](/img/PR/3/krivuljeBad.jpg)

## 1.4. Prikaz deležev

- Čas teče po osi X
- Problem skale
  - Prva kaže med 0 in 100, majhne razlike.
    - Manjka horizontalna črta 50
  - Druga kaže med 38 in 46, razlike so videti ogromne
    - Dramatične spremembe, ki pa niso resnične (50 niti ni na skali)
- Spodnja desna slika je pristranska do (manj favorizirana) Christie
  - Občutek gravitacije

![delezi](/img/PR/3/delezi.jpg)

### 1.4.1. Primer več krivulj

- Višina povprečne letne plače glede na število let izobrazbe
- Daljše izobraževanje, višja plača. Razlike se z leti manjšajo.
- Primerjava miški in ženska težka, ker grafa na različnih grafih, z dvema različnima skalama!
- Ženska s 16 leti izobraževanja (najvišja spodaj) plačana enako kot moški (8-11) leti.

![krivuljeDelezi](/img/PR/3/krivuljeDelezi.jpg)

### 1.4.2. Manipuliranje - pritoževanje nad šolninami

![manipulacija podatkov](/img/PR/3/solninePrimer.jpg)

**_Podrobnosti manipulacije_**

![podrobnostiManipulacije](/img/PR/3/podrobnostiManipulacije.jpg)

## 1.5. Linerana ali logaritemska skala

- **_Logaritemsko skalo uporabljamo, ko vemo da proces, ki generira vrednosti je eksponenten_**

![logSkala](/img/PR/3/logSkala.jpg)

## 1.6. Krivulje - referenčna vrednost

- Pomembna je referenčna vrednost

![refVrednost](/img/PR/3/refVrednost.jpg)

- Pri risanju krivulj se izogibajmo pisanje informacij na graf - preveč informacij na grafu
- Raje naredimo tabelo vrednosti

![krivulje3](/img/PR/3/krivulje3.jpg)

## 1.7. Slike več spremenljivk hkrati

### 1.7.1. Scatter Plot - razsevni diagram

![scatterPlot](/img/PR/3/scatterPlot.jpg)
![scatterPlot2](/img/PR/3/scatterPlot2.jpg)

- Lahko dodajamo dodatne atribute
  - Barve
    - ozadje
    - točke
- Iskanje osamelcev **_outliers_**

- Iskanje osamelcev v **Orange-u**

![orange1](/img/PR/3/orange1.jpg)
![orange2](/img/PR/3/orange2.jpg)
![orange3](/img/PR/3/orange3.jpg)
![orange4](/img/PR/3/orange4.jpg)

- Čas v razsevnem diagramu

![timeScatterPlot](/img/PR/3/scatterPlot3.jpg)

:::note
**_VizRank_** -> Brute force algoritem za iskanje ustreznih kombinacij (os X Y) za vizualizacijo.
:::

### 1.7.2. RadViz

![radviz](/img/PR/3/radviz.jpg)
![radviz2](/img/PR/3/radviz2.jpg)

### 1.7.3. PolyViz

:::note
Odločiti se moramo, kako obrniti os (min -> max max -> min)
:::

![polyViz](/img/PR/3/polyviz.jpg)

### 1.7.4. Vzporedne koordinate

:::note
Odločiti se moramo, kako obrniti os (min -> max max -> min)
:::

![vzporedneKoordinate](/img/PR/3/vzporedneKordinate.jpg)

### 1.7.5. Sievov diagram

:::note

- Dobimo ven različne deleže, ki predstavljajo zanimive zakonitosti v podatkih
- Npr. povezava med spolom in preživetje
- Hitro vidimo kombinacije, ki izstopajo

:::

![sieve](/img/PR/3/sieve.jpg)

### 1.7.6. Parketni diagram (mosaic)

- Lahko vidimo, katera kombinacije atributov soupadajo z drugo kombinacijo

![mosaic](/img/PR/3/mosaic.jpg)

### 1.7.7. Kviz

![kviz](/img/PR/3/kviz3.png)
