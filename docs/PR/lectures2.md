# 1. Podatki, pridobivanje in predprocesiranje

80% časa pri PR gre za pripravo podatkov.

Kako pridobivamo podatke _!!!_:

- iz spleta
  - **Beatiful Soup**
  - **Selenium** za branje dinamično generirane vsebine (headless browser)
- Diskrecija podatkov
- Imputicija
  - Vstavljanje manjkajočih vrednosti

## 1.1. Diskretizacija

:::note

Iz zveznih vrednosti dobimo diskretne. **_Cilje je zmanjšati merske napake (šum) v podatki_**

:::

- Opis in primeri različnih diskretizacij. Primer **scikit-learn** -> knjižnica za data mining.

- Način diskretizacije:
  - uniform -> enake škatlice -> pade enako točk
  - quantile -> škatle so ozke v bližini gruč
  - kmeans -> najprej se gruči in nato postavi škatlice
- **Orange** tudi ponuja možnost diskretizacije

Da se delati tudi obratno. Iz diskretnih vrednosti dobimo zvezne vrednosti.

## 1.2. Imputacija

:::note

Podatki manjkajo zaradi dveh razlogov:

- Se ga ne da izmeriti (odpove merilna naprava)
- Se ga ne more izmeriti (Nekaj pove, da podatek manjka)

:::

[Imputacija SciKit Learn](https://scikit-learn.org/stable/modules/impute.html "Imputacija")

TODO: Try SciKit learn

## 1.3. Vizualizacija

- Tortne diagrame težko primerjamo -> Slab prikaz podatkov

SLika Torte

- Boljša alternativa pie charta so štrudlji

Slika štrudl-plot

- Primer slabo izbrane barve, naravno branje diagramov (čas leva proti desni)
- Boljši način primerjave deležev v času je line graph (vidimo trende, malo oznak, oznake x-osi so tudi glava tabele)

:::note

**_Vzorci v podatkih + tabele is king_**

:::

Slika line graph

- Slab primer je tudi skakanje po radar plotu, slabo za primerjavo

- prikaz časa -> **_linegraph z jasnimi barvami_**

### 1.3.1. Primer | Štrudelj plot > Pie Chart | 'Three Years of Murder in New York City'

![ThreeYearsOfMurderInNYC](/img/PR/2/threeYearOfN.jpg "štrudl")

### 1.3.2. Kviz

![kviz2](/img/PR/2/kviz2.png)
