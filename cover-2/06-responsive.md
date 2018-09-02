# Responsivt

{% hint style="info" %}
**MDN**:

* [Using media querie](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)[s](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Values_and_units)
* [Values and units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Values_and_units)
{% endhint %}

Når vi jobber med web, må vi tilpasse oss det faktum at brukerne våre kan aksessere siden vår fra en mengde forskjellige skjermstørrelser. Det er viktig at vi tenker på dette og lager gode sider både på desktop og mobile enheter som skalerer bra. Det gjelder også for brukere som zoomer inn på siden.

## Media queries

Media queries, også omtalt som breakpoints, er det vi kan bruke når vi vil style innhold tilpasset bestemte skjermstørrelser.

```css
@media statement {
    ...;
}
```

AND operator

```css
@media tv and (min-width: 700px) and (orientation: landscape) {
    ...;
}
```

OR \(,\) operator

```css
@media (min-width: 700px), handheld and (orientation: landscape) {
    ...;
}
```

NOT operator

```css
@media not all and (monochrome) {
    ...;
}
```

## Relative enheter

I stedet for å bruke `px`, som er en fast størrelse uavhengig av zoom, bør man bruke `em` eller `rem`.

