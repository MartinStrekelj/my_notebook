# 1. Aritmetični kod in entropija

zvezek

## 1.1. Stiskanje slovarja

:::note

- Ne rabimo verjetnosti
- Kodirnik
  - Sproti gradimo slovar
  - Sklicevanje na nize v slovarju
- Dekodirnik
  - Sporti gradi slovar (rekonstrukcija slovarja)
  - Dekodira znake

:::

### 1.1.1. Algoritem LZ77 (Lempel-Ziv)

:::note

- Kodirnik
  - Preiskuje že videno besedilo
  - V njem išče najdalši niz, ki se je ponovil
  - Ko najde niz poda referenco na niz

:::

zvezek

Za krajše odmike imamo tudi krajše kodne zamenjave.

![dekodiranje](/img/TIS/4/dekodiranjeLZ77.jpg)

### 1.1.2. Deflate

:::note

- Malce predelan LZ77
- Par (odmik, dolžina) ali osnovni znak

:::

zvezek

### 1.1.3. Kanonični Huffmanov kod

:::note

- Zgradimo Huffmanovo drevo in iz njega razberemo dolžine kodnih zamenjav
- Osnovne znake razvrstimo(po kriterijih):
  - dolžine kodne zamenjave
  - abeceda (nek vrstni red)
- Prvemu znaku dodelimo same ničle (binarno ničlo)
- Kodo za nasledni znak dobimo tako, da prejšni kodi binarno prištejemo 1
- Če je kodna zamenjava daljša od binarne kode števila, na koncu dodamo 0

:::

Primer zvezek

Vsa informacija, ki jo moramo posredovati preko kanala je **_vrstni red in število znakov kodne zamenjave posameznega znaka_**
