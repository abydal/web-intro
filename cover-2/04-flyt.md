# Flyt

## Flyt

### Display

CSS-egenskapen `display` sier noe om hvordan et element skal legge seg i flyten på siden. Med flyten mener vi rekkefølgen på elementene i leseretning, fra øverst i venstre hjørne til nederst i høyre hjørne. Hvis man ikke definerer noe annet vil to sekvensielle HTML-elementer legge seg i den rekkefølgen de er definert i HTML-strukturen.

Nederst i [kapittelet om HTML-elementer](https://github.com/bekk/web-intro/tree/645b85b7c83346bcb1576cba234407c4d12e6175/03-css/02-html/01-elementer.md) beskrev vi hvordan block- og inline-elementer oppfører seg. De forskjellige HTML-elementene har alle forskjellig default-verdi for `display`:

```markup
<div>
  <h1>Overskrift</h1>              <!-- block -->
  <p>Litt tekst</p>                <!-- block -->
  <button>En knapp</button>        <!-- inline-block -->
  <button>Enda en knapp</button>
  <a href="#">Lenke</a>            <!-- inline -->
  <div>mer tekst</div>             <!-- block -->
</div>
```

## Overskrift

Litt tekst En knapp Enda en knapp [Lenke](04-flyt.md)mer tekst

### Midtstilling

Med `text-align` kan vi velge om tekst skal være venstre-, midt- eller høyrejustert innenfor et block-element.

```markup
<div class="midtstilt">Midtstilt?</div>
```

```css
.midtstilt {
    text-align: center;
}
```

Midtstilt?

`div` er et block-element og teksten blir midtstilt.

```markup
<span class="midtstilt">Midtstilt?</div>
```

```css
.midtstilt {
    text-align: center;
}
```

Midtstilt?

Siden `span` er et inline-element kan vi ikke posisjonere tekst innenfor elementet, det har rett og slett ikke noe ledig rom rundt seg det kan plassere seg relativt til.

Hvis vi vil midtstille et element innenfor sitt forelder-element kan vi bruke `margin`.

```markup
<div class="midtstilt-blokk">Midstilt blokk</div>
```

```css
.midtstilt-blokk {
    width: 400px;
    margin-left: auto;
    margin-right: auto;
}
```

Midtstilt blokk

#### Tips

> Som dere snart vil finne ut, er det flere egenskaper som bare fungerer på block- eller inline-block-elementer. Dette gjelder både `text-align`, som forklart over, i tillegg til `margin`. Dette kan være en kilde til vanskelig debugging når stilene våre tilsynelatende ikke treffer. Heldigivs pleier DevTools å vise oss hvilke stiler som ikke fungerer fordi de ikke er gyldige i Styles-panelet når vi inspiserer koden vår.

### Posisjonering

Inspiser disse elementene i DevTools:

 A B C

Elementene har statisk posisjon. Det betyr at de plasseres slik de ligger i HTMLen og ikke blir påvirket av posisjonsegenskapene `top`, `right`, `left`, `bottom` og `z-index`.

Endre element B til å ha `position: relative`. Ser du noen forskjell? Relativ posisjon betyr at elementet ligger på sin statiske posisjon, men at endringer i posisjonsegenskapene vil få elementet til å flytte seg _relativt til sin egen posisjon_. Sett verdiene `top` og `left` for element B til å være 15px. Legg merke til at C ikke flytter på seg. Den opprinnelige avholdte plassen til B er den samme som før.

Endre nå element B til å ha `position: absolute`. Hvor ble elementet av? Med absolutt posisjon vil elementet forholde seg til posisjonsegenskapene `top`, `left` osv innenfor nærmeste posisjonerte forelder - eller rotelementet. Med absolutt posisjon blir det ikke holdt av plass til element B mellom A og C.

Se på `article`-elementet som ligger rundt A, B og C. Gi den `position: relative`. Hvor ble nå B av? Nå som `article` er posisjonert vil B forholde seg til den i stedet for rotelementet.

### Oppgaver

* [Midtstilling](https://jsfiddle.net/Matsemann/wg8oLh8a/)
* [Posisjonering](https://jsfiddle.net/Matsemann/b75wz3mj/1/)

