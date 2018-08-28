# DOM-apiet

> **MDN**:
>
> * [Oversikt over DOM- og HTML-interfaces](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)

Javascript gir oss et rikt API mot [DOMen](../cover-1/07-dom.md) via document-objektet. Hvis HTML-en inneholder dette...

```markup
<img id="mainpicture" src="http://placekitten.com/200/300">
```

... så kan vi aksessere den slik:

```javascript
const img = document.querySelector('#mainpicture');
```

```markup
<div id="boks">
    <a href="mer.html">Klikk her</a> for å lære mer
</div>
```

```javascript
const boks = document.querySelector('#boks');

boks.innerHTML; // <a href="mer.html">Klikk her</a> for å lære mer
boks.textContent; // Klikk her for å lære mer
```

## Hendelser

Med DOM-apiet kan vi også legge til hendelser når noe skjer med et DOM-element. Vi gjør dette ved å legge på lyttere som venter på at en gitt hendelse skal skje, f.eks. et klikk på en knapp:

```javascript
document.querySelector('#boks').addEventListener('click', function() {
    // Gjør noe gøy når boks har blitt trykket på!
});
```

Vi kan også erstatte innhold med noe annet. Kjør den følgende kodesnutten i consolet på denne siden. Ser du ut fra koden hva som skjer når du nå trykker på bildet av apen?

```javascript
document.querySelector('#danse-ape').addEventListener('click', function() {
    const el = document.querySelector('#danse-ape');
    const src = el.getAttribute('src').replace('.png', '.gif');
    el.setAttribute('src', src);
});
```

![](../.gitbook/assets/danse-ape.png)

## Oppgaver

* [Test ut DOM-apiet](http://jsbin.com/povoyoz/24/edit?js,console)
* Fortsett med knappene du lagde i [kapittel 2](https://github.com/bekk/web-intro/tree/645b85b7c83346bcb1576cba234407c4d12e6175/02-html/06-knapper/README.md).
  * Legg til unike `id`-attributter på `output` og `button`-elementene.
  * Legg til hendelseshåndtering av knappene i JS-filen du lagde i forrige seksjon. Legg til en click event handler som legger til 1 på tallet i `output` når man trykker på plussknappen.
  * Legg til en click event handler som trekker fra 1 fra tallet i `output` når man trykker på minusknappen.

