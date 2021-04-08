# Večrazsežno lestvičenje (MDS -> multidimensional scaling)

slika

## Odkrivanje skupin

slika

Poišči skupine primerov tako, da bo vsaka skupina vsebovala le podobne objekte.

- Koliko skupin?
- Lahko ponavljamo skupine do konca (ena točka na skupino)

## Metode za razvrščanje v skupine

- Delitev primerov (Partitional clustering)
  - Primere delimo v neprekrivajoče skupine (clusters)
  - Primer: metoda voditeljev(k-means clustering)
    - Določitev parametra
    - Vsako skupino predstavimo s njenim centrom / voditeljem
    - Vsak center tvori svojo skupino

### K-means

![vod](/img/PR/5/voditelji.jpg)

K-means

- Začetni voditelji so izbrani naključno
  - Metoda je občutljiva na izbiro

...

![primerKmeans](/img/PR/5/primerKmeans.jpg)

![gostoteSkupin](/img/PR/5/gostoteSkupin.jpg)

### Hierarhično razvrščanje

- Rezutat je hierarhija skupin primerov
- Prikažemo z dendrogramom
  - Iz drevesa je razvidno, kako so se združevale skupine

![dendrogram](/img/PR/5/dendrogram.jpg)

- Podobnost med skupinami (inter-cluster similarity)

![podobnostSkupin](/img/PR/5/razdaljeSkupin.jpg)
![hierarhija](/img/PR/5/hierarhicnorazvrscanje.jpg)
![compleLinkage](/img/PR/5/completelinkage.jpg)
![linkage](/img/PR/5/linkage.jpg)

### Kvaliteta razbitja (Silhouette score)

![kvaliteta](/img/PR/5/kvalitetaRazbitja.jpg)
![silhueta](/img/PR/5/silhueta.jpg)
