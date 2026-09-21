# Imatges

## El logo

`logo.svg` d'aquesta carpeta és **provisional**: una rosa oberta dins d'un plat,
dibuixada amb els colors de la marca. Serveix perquè el lloc no quedi coix,
però el vostre logo real és millor.

He localitzat el logo original al blog antic, però el meu entorn no té permís
per descarregar de `blogger.googleusercontent.com`. El podeu baixar vosaltres
des d'aquí:

```
Logo (196 px)
https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjcTGjGuK2Rib-fQ2t-suHSjHYXcqwE_F3RcbbzhvUIzmFtLWY3hjg6YwqbVRTNg9rjmmL4RBFhCyoPrSIBZKp8e-215sjKjUNiITOZF_kFhj3O5DEDQquhZA9Vy4UcPfFDLWO4ke6X3_A/s196/Logo+3x2+cm.jpg

Capçalera del blog, 828 px (bona candidata per a cuina.jpg)
https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhyKSt4flDWLYEeh8MNnYtbjuJfLv5NjF6kKCRVZUMUQYa7q_fNVblPYPeJzPcUlQfIST2ruKQCojXL-1wuFui3ROON3HrMGWzfyNJH4Z61OTbQW-dIPrCCQpic1KK8gyGJrK5ymJzvHio/s828/portapetit.jpg

Il·lustració de l'escola de cuina (bona per a taller.jpg)
https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhjnPxXXcVpA-xzq04w6KyorXBu39ZYmXYqymSBs7oAQFHbFDXi6MS8pUlqFz_aGIAufzvYumXk65zpM0lAR2oB0wUwISjoGNm_GSdRWScIo-FNd3sYxqM3JKXHUo4djzqNBftuW68-UJk/s1600/escolaCuinaIlustra.png

Fotos del monogràfic de cuina vegetariana (bones per a taller.jpg o catering.jpg)
.../s1600/IMG-20171111-WA0007.jpg
.../s1600/IMG-20171111-WA0009.jpg
.../s1600/IMG-20171111-WA0011.jpg
.../s1600/IMG_20171111_134755.jpg
```

Les trobareu totes a `http://menjadorcalarosa.blogspot.com/`. També teniu
material millor i més recent a l'Instagram `@menjadorcalarosa`.

Per substituir el logo: deseu el vostre com a `logo.svg` (ideal) o
`logo.png` en aquesta carpeta. Si feu servir PNG, canvieu `logo.svg` per
`logo.png` a `generar.py` i torneu a generar, o feu un cerca-i-substitueix
als vuit fitxers HTML.

## Les fotos

Deseu-les amb aquests noms exactes i cap codi no s'ha de tocar:

| Fitxer          | On surt                          | Què hi hauria d'haver |
|-----------------|----------------------------------|------------------------|
| `cuina.jpg`     | Portada, principal               | L'equip cuinant. La imatge més important del lloc. |
| `taula.jpg`     | Portada, secció de cultura       | Criatures parant taula o dinant, en vertical |
| `catering.jpg`  | Pàgina de càtering               | Taula parada, plats de temporada |
| `menjador.jpg`  | Pàgina de menjador infantil      | Una hora de dinar real |
| `casal.jpg`     | Pàgina de casals                 | Criatures cuinant o a l'hort |
| `taller.jpg`    | Pàgina de tallers                | Mans treballant, primer pla |
| `cistella.jpg`  | Pàgina de cistelles              | Cistella de verdura de temporada |
| `equip.jpg`     | Pàgina de qui som                | Les sòcies de la cooperativa |
| `espai.jpg`     | Pàgina de contacte               | La façana o l'entrada del local |
| `og.jpg`        | Previsualització a xarxes        | 1200 × 630 px exactes |

**Mentre no hi siguin, no es trenca res.** Cada marc mostra un degradat càlid de
fons, així que el lloc es veu acabat encara que la carpeta estigui buida. Les
fotos apareixen soles a mesura que les aneu posant.

### Recomanacions

- Amplada 1600 px, format JPG de qualitat 80, o WebP si el vostre allotjament
  el serveix. Cada foto per sota de 250 KB.
- Millor fotos vostres reals, encara que no siguin perfectes, que banc d'imatges.
  Una cuina de veritat amb gent de veritat converteix molt més.
- **Consentiment d'imatge:** per a qualsevol foto on es reconeguin criatures cal
  autorització escrita de les famílies. Si no la teniu de totes, trieu plans on
  no se'ls vegi la cara: mans, esquenes, plans generals, detalls del plat.

### Text alternatiu

Ja està escrit a l'atribut `aria-label` de cada marc de foto dins dels HTML.
Si canvieu el contingut d'una imatge, actualitzeu també aquesta descripció:
és el que llegeix Google i el que sent una persona cega.
