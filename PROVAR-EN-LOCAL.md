# Provar la web en local (i que el formulari funcioni)

## El problema

Si obriu `index.html` amb doble clic, el navegador carrega la pàgina com a
fitxer (`file://...`). El formulari fallarà amb aquest missatge:

> Unable to submit form. Make sure you open this page through a web server.

No és un error de la web. FormSubmit rebutja els enviaments que venen d'un
fitxer local perquè no en pot verificar l'origen. Cal servir la carpeta des
d'un servidor, encara que sigui al vostre propi ordinador.

## Solució ràpida: servidor local

Obriu una terminal dins de la carpeta de la web i executeu:

```
python3 -m http.server 8000
```

A Windows, si `python3` no funciona, proveu `py -m http.server 8000`.

Després aneu al navegador i entreu a:

```
http://localhost:8000/
```

Ara la web es serveix per HTTP i el formulari ja pot enviar.

Per aturar el servidor, premeu Ctrl+C a la terminal.

## Solució definitiva: publicar-la

El més senzill és Netlify Drop: entreu a `app.netlify.com/drop` i arrossegueu
la carpeta. En menys d'un minut tindreu una adreça pública real on tot
funciona, inclòs el formulari.

## El primer enviament

Amb FormSubmit, el primer cop que s'envia el formulari rebreu un correu a
`eco@menjadorcalarosa.com` demanant que confirmeu l'adreça. Fins que no
cliqueu l'enllaç, els missatges no arriben. Només cal fer-ho una vegada.

Un cop activat, us donaran un codi. Si voleu que l'adreça no quedi visible
al codi font, substituïu a `text_form.py`:

```
action="https://formsubmit.co/eco@menjadorcalarosa.com"
```

pel codi que us donin:

```
action="https://formsubmit.co/EL-VOSTRE-CODI"
```

## Si publiqueu a Netlify

No cal cap servei extern. A `text_form.py`, canvieu:

```python
MOTOR = "formsubmit"
```

per:

```python
MOTOR = "netlify"
```

i torneu a generar. Els missatges queden al panell de Netlify i us els
reenvia al correu que hi configureu, sense activació ni tercers.

## Enllaços sense .html (actualitzat 2026-09-24)

Els enllaços interns ara apunten a URLs netes (`/contacte`, no `/contacte.html`),
igual que les serveix Cloudflare Pages. `python3 -m http.server` no sap trobar
`contacte.html` a partir de `/contacte`, així que en local aquests enllaços donaran 404.
Per provar-ho igual que a Cloudflare:

```
npx wrangler pages dev .
```
