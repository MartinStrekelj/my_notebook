## Kod LZW

:::note

**Kodiranje**

1. Definiranje osnovnega slovarja
2. Dopolnjevanje slovarja
3. Iščemo podobne nize in ponavljamo
   1. N = ''
   2. Preberemo znak v našem dokumentu (z)
   3. Pogledamo če je niz sestavljen iz [nz] (kontagenacija)
   4. Ali je [nz] v slovarju?
      1. DA? -> N=[nz]
      2. NE? -> izpišemo indeks k niza N in dodamo niz [nz] v slovar
4. Za zadnji niz izpiši indeks k niza N

:::

:::note

**Dekodiranje**

1. Preberemo indeks
2. V slovarju poiščemo niz N, ki ustreza indeksu k -> izpiši N
3. N'star = N
4. Ponavljamo
   1. Preberi indeks k
   2. v slovarju poiščemo N za K
   3. izpišemo N
   4. v slovar doda [N'star N(1)]
   5. N'star = N

:::

## Verižno kodiranje (run-length encoding)

Primeri: BMP, TIFF, PCX

- Enostavna izvedba
- Podatki se ponavljajo
  - aaaabbccc -> 4a2b3c

BMP

- Lahko kodira verižno
- Ali ne kodira -> prvi bajt v bloku pove za kakšen način kodiranja gre
  - 0 verižno - 1 osnovni znaki
  - Ostalih 7b pove število znakov
  - |0|10|115 -> 10x po 115 znakov
  - 1|3|11|12|110 -> rgb stiskanje

Faksiranje sporočil

## Stiskanje z izgubami

- Bistveno bolje lahko stisnemo
- Kompresijsko razmerje
  
- brez izgub -> datoteke,exe, koda 50%-75%
- z izgubami -> slike, zvok, video posnetki - 10%
  - Vsebine, ki jih zaznavamo s čutili
  - Psiho vizualni
  - psiho akustični pristopi

## JPEG

1. Pretvorba formata:
   1. RGB -> yCrCb kjer 
      1. y -> svetlost
      2. CrCb -> kroma
      3. npr: 4:2:2 ali 4:1:1

2. Vsaka od treh komponent se obdeluje posebaj na enak način
   1. 2D diskretna cosinusna transformacija
   2. Lahko odrežemo velike koeficiente
      1. Manj natančno shranjeno

3. Shranjujemo razliko med D in D' (D' = B+C-A)

4. Po sliki se sprehajamo cigcag po diagonali.
slika
5. Razlike so si podobne -> Verižno kodiranje razlik **(RLE)**.
6. Na dolžinah Huffmann. (dokler je bil aritmetični kod še pod IBM patentom)

## MP3

1. Diskretna kosinus transformacija
slika
2. Namesto L&R -> L & (R-L)
3. Zelo nizke frekvence -> mono zvok + nekaj dodatnih bitov (za delno rekonstrukcijo prostorskega zvoka)
4. spreminajnje koeficientov diskretne kosinusne transformacije
5. Huffmanovo kodiranje

## MPEG

- slike : JPEG
- Audio : MP3
slika
- okvir:
  - I -> cela slika kodirana kot JPEG
  - P -> prediktno kodiranje (vektor premika + sprememba)
  - B -> kodiranje iz predhodnega in naslednjega okvira
  - D -> močno stisnjena cela slika (I)