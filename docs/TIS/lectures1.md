# 1. Uvod

:::note
**TIS sloni na 5 temeljih:**

- entropija
- kriptologija
  - entropija
  - kompleksnost
- širjenje informacij
- obdelava podatkov
- ekonomija (ne bomo veliko poudarjali pri tem predmetu)
:::

Velik fokus pri predmetu bo na entropiji, širjenje informacij, odbdelava podatkov (malo tudi kriptografija)

TIS je 'nastaja' zadnjih 100 let. Začetek **Shannon 1948 -> 'Teorija komunikacij'** matematična teorija [teorija tldr](https://www.communicationtheory.org/shannon-and-weaver-model-of-communication/ "Shannon 1948 -> 'Teorija komunikacij'"). Zaposlil se je pri močni ameriški IKT firmi z močnim razvojem. Potreba po zanesljivosti prenosa in vprašanje kako zmanjšati napako.

    - 0 -> 1
    - 1 -> 0
    Ideja dupliciramo prenos
    0 -> 000 -> 010 -> 0
    aha poslali so ničlo 0>1 ničel več kot enic

Zanašamo se na verjetnost, ker je verjetnost, da se bosta dve ničli (bita) obrnila je manjša.
Večja zanesljivost je več znakov namesto 3 (npr 5., 7.). Posledično se tudi poveča čas prenosa podatkov.

Shannon:

- Eupeka -> Eureka (dobimo s sklepanjen)

Torej iz vsebine sporočila lahko sklepamo, kaj je bilo poslano.

To tehnologijo uporablja CRC.

![Teorija komunikacij img](/img/TIS/1/shannon_weaver_model.jpg "Teorija komunikacij")

## 1.1. Splošno

Sprotne obveznosti

- 4x DN
- Tedenski kvizi (neobvezno)

Končna ocena:

- 1/3 iz vaj
- 1/3 izpita - računski del (uporabne naloge)
- 1/3 iz teoretičnega dela

Literatura:

- izpiski (plonkci Uroša)
- lastni zapiski (this + zvezek)
- Lunberger: Information Science, 2006
- Pavešič: Informacija in kodi, FE & FRI, 1997

## 1.2. Informacija

Prvi, ki se je z terminom 'koliko informacije je v enem dogodku' ukvarjal **_Hartley (1928)_**.

Obravnaval je sporočila.

V vsakem momentu se ti lahko zgodi **_n različnih stvari (dogodkov)_**.

**_(dogodek je met kovanca, rezultat je grb/cifra) -> n = 2_**

met kocke -> n = 6 (6 izidov)

Kaj če dogodek z **n** izidi ponovim **l** krat.

Funckija, ki bo podajala informacijo => f(n^l) = l * f(n)

![Rokopis1](/img/TIS/1/rokopis.jpg "Lastna informacija")

Informacijo lahko merimo s funkcijo, ki je **logaritem (Hartley)**

**_Shannon (1948) izpostavi dejstvo, da vsi izidi dogodka niso enako verjetni_**

![Rokopis2](/img/TIS/1/rokopis2.jpg "Entropija")

Lastna informacija opisuje dogodek za nazaj -> kar se je že zgodilo.

## 1.3. Entropija

:::note

- Ocena za (povprečno) informacijo, ki jo bomo dobili
- Povprečna lastna informacija -> upošteva vse izdide
- je mera za nedoločenost dogodka

:::

Koliko informacije (to lahko merimo v enoti bit, trit, hartley... izhaja iz osnove logaritma) lahko pričakujemo za dogodek, ki se ni še zgodil (v povprečju).

![Rokopis3](/img/TIS/1/Rokopis_2021-02-22_3.jpg "Entropija")

### 1.3.1. Lastnosti entropije

:::note

- je zvezna funkcija
- je simetrična funkcija
- H(x) >= 0
- je navzgor omejena z log_b n
- je aditivna, če so dogodki neodvisni

:::

![Rokopis4](/img/TIS/1/Rokopis_2021-02-22_4.jpg "Lastnosti entropija")

### 1.3.2. Primeri

![kviz5](/img/TIS/1/kviz1.png "primeri")
