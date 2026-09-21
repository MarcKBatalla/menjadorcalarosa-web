# Menjador Ca la Rosa — web estàtica

## Què és

Vuit pàgines en HTML pur. **Zero JavaScript, zero framework, zero base de dades.**
Tot el contingut és al HTML des del primer byte: Googlebot el llegeix sense
haver de renderitzar res.

```
index.html                        Inici
menjador-infantil.html            Menjador infantil ecològic
catering-sostenible-barcelona.html  Càtering  ← la pàgina comercialment més important
casals-i-activitats.html          Casals i lleure
tallers-de-cuina.html             Tallers de cuina
cistelles-ecologiques.html        Cistelles i menús per a gent gran
qui-som.html                      La cooperativa i el Mercat de Pagès
contacte.html                     Contacte

assets/estil.css                  Full d'estils únic
sitemap.xml                       Mapa del lloc
robots.txt                        Sense cap bloqueig
.htaccess                         301 des de les URLs antigues + capçaleres
```

## El problema de l'entorn actual

L'allotjament compartit fa una redirecció que impedeix la indexació. Sigui quin
sigui l'entorn nou, cal comprovar tres coses **abans** de donar el lloc per bo:

1. `curl -I https://menjadorcalarosa.cat/` ha de tornar **200**, no 301 ni 302.
2. La resposta **no** ha de portar cap capçalera `X-Robots-Tag: noindex`.
3. `curl -s https://menjadorcalarosa.cat/ | grep "Cuinem amb"` ha de trobar el text.
   Si no el troba, el contingut depèn de JS i tornem al mateix problema.

Si passa les tres, està resolt.

## Desplegament

Com que no hi ha res dinàmic, serveix qualsevol allotjament estàtic. Per ordre
de recomanació per a aquest cas:

- **Netlify o Cloudflare Pages** — gratuïts en aquest volum, HTTPS automàtic,
  desplegament arrossegant la carpeta. Cap servidor compartit pel mig i, per tant,
  cap redirecció heretada. És l'opció que trencaria el problema d'arrel.
  (Amb Netlify, les regles de `.htaccess` es tradueixen a un fitxer `_redirects`.)
- **Allotjament Apache propi** — puja la carpeta sencera a l'arrel del domini.
  El `.htaccess` ja porta les 301 i les capçaleres.

Verifica que el `.htaccess` s'ha pujat: molts clients FTP amaguen els fitxers
que comencen amb punt.

## El primer dia després de publicar

1. Google Search Console: verifica la propietat i envia `sitemap.xml`.
2. Fes servir "Inspecció d'URL" a la home i prem **Sol·licita la indexació**.
   Repeteix-ho amb `catering-sostenible-barcelona.html` i `menjador-infantil.html`.
3. Bing Webmaster Tools: el mateix. Costa cinc minuts i és tràfic gratis.
4. Prova el marcatge a `search.google.com/test/rich-results`. Hauria de detectar
   `LocalBusiness`, `Service`, `FAQPage` i `BreadcrumbList`.

## Fitxa d'empresa a Google (això mou l'agulla més que la web)

Per a un negoci de barri, el perfil de Google és sovint més decisiu que el lloc web.

1. Reclama o crea el perfil a `business.google.com`.
2. Categoria principal: **Servei de càtering**. Secundàries: cooperativa,
   servei d'àpats, centre d'activitats infantils.
3. El NAP ha de ser **idèntic, caràcter per caràcter**, al del peu d'aquesta web:
   `Carrer de Mossèn Juliana, 23, 08027 Barcelona` · `651 425 292`
4. Puja fotos reals de la cuina, dels plats i de l'espai. Les fotos genèriques
   no aporten res.
5. Demana ressenyes a les famílies del menjador. Cinc ressenyes honestes valen
   més que qualsevol altra cosa d'aquesta llista.

## Corregir el NAP a fora

Aquestes fitxes existeixen i tenen errors. Corregir-les és feina d'una tarda i
té efecte directe sobre el posicionament local:

- **bcnsostenible.cat** — les coordenades estan invertides (latitud 2,18 /
  longitud 41,42 us situa al golf de Guinea). Cal que siguin
  latitud **41.4237594**, longitud **2.1898681**.
- **Guia del districte de l'Ajuntament** — apareixeu alhora a Horta-Guinardó i a
  Sant Andreu. Cal deixar només Sant Andreu.
- **Coop57** — hi consta el blog antic de Blogspot i el correu de Gmail. Actualitzar
  a `menjadorcalarosa.cat` i `eco@menjadorcalarosa.com`.
- **Cooperatives de Treball, Ruralitzem, Àgora Pagesa** — comprovar telèfon i web.

Un sol telèfon i un sol correu a tot arreu. Ara mateix en circulen dos de cada.

## Disseny

Paleta: rosa gerd (el color de marca, pel nom), pruna fosca, mel i verd d'herba
sobre una nata càlida. Cantonades molt arrodonides, ombres suaus i botons de
píndola. Tipografies Fraunces (titulars, serif tova) i Figtree (text).

## Coses que no he inclòs i per què

- **Imatges i logo.** Vegeu `assets/img/LLEGEIX-ME.md`: hi ha els enllaços
  directes al logo i a les fotos del blog antic, i la taula de noms de fitxer.
  Fins que no les poseu, cada marc mostra un degradat càlid i el lloc es veu
  acabat igualment.
- **Versió en castellà.** La web és en català perquè el públic és de barri.
  Quan la vulgueu, es duplica a `/es/` i s'afegeixen etiquetes `hreflang`
  a totes dues versions.
- **Blog.** Recomanable, però només si algú l'escriu de veritat. Un blog
  actualitzat per última vegada el 2017 fa més mal que no tenir-ne.
- **Botiga.** L'antiga era WooCommerce. Si la voleu recuperar, el més net és un
  subdomini `botiga.menjadorcalarosa.cat` perquè el pes del WordPress no torni a
  afectar la velocitat del lloc principal.

## Manteniment

La banda taronja de la portada («Ara a taula, al setembre») s'ha d'actualitzar
cada mes o dos. És contingut fresc que Google nota i, sobretot, és honest amb
el que hi ha realment a la cuina. Està al principi de `index.html`, dins de
`<section class="temporada">`. Canviar la llista de fruites i verdures és
l'única tasca recurrent que necessita aquesta web.
