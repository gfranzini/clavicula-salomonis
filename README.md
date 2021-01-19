# Clavicula Salomonis

Diplomatic TEI transcription of [Ms. Codex 1673](http://dla.library.upenn.edu/dla/medren/detail.html?id=MEDREN_9962943583503681).
Transcribed for the [_Verba Bestiae_](https://github.com/CIRCSE/VerbaBestiae) project. 


## Encoding criteria

- It's not always 100% clear whether the first letter of a word is in capitals. I try to maintain capitalisation in the transcription.
- I remove the last line of one folio if repeated on the next folio.


### Encoding Check-list

- paragraphs
- abbreviations
- emphasis
- special characters
- ligatures
- additions and deletions  


## Encoding examples

### Ligatures and special characters

- Digraphs/Ligatures: Æ, æ, ﬅ, et, ÿ, &
- Special characters: ę, ſ


<!-- 'de' ligature?-->


In `<teiHeader>`

```
<encodingDesc>
    <charDecl>
        <glyph xml:id="AElig">
            <localProp name="name" value="Latin Capital Ligature AE"/>
            <mapping type="standard">Æ</mapping>
            <mapping type="PUA">U+00C6</mapping>
        </glyph>
        <glyph xml:id="ecaud">
            <localProp name="name" value="Latin Small Letter E with Ogonek"/>
            <mapping type="standard">ę</mapping>
            <mapping type="PUA">U+0119</mapping>
        </glyph>
        <glyph xml:id="et">
            <localProp name="name" value="Ampersand"/>
            <mapping type="standard">&amp;</mapping>
            <mapping type="PUA">U+0026</mapping>
        </glyph>
    </charDecl>
</encodingDesc>
```

In `<body>`

```
<lb n="1"/>Initium nostr<g ref="#aelig">ae</g> clavis inquit Salomon filius Da
```

```
<lb n="2"/>necessaria prius pr<g ref="#ecaud">e</g>parare oportet, ut in sequenti
```

```
<lb n="27"/>mine Adonay <g ref="#et">et</g>c. ut in 2. Libro.
```

TEI references:
- `<charDecl>` element: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/examples-charDecl.html
- `<g>` element: https://tei-c.org/release/doc/tei-p5-doc/en/html/ref-g.html
- `<glyph>` element: https://tei-c.org/release/doc/tei-p5-doc/en/html/ref-glyph.html


### Addition

```
<lb n="109"/>nerearum, ac pulverum, quae ad ph<add place="above">r</add>aeneses, aliaque
```

```
<lb n="114"/>dei, videlicet: ad orientem El. <g ref="#acircum">a</g><add type="partial" place="inline">d</add> occidentem
```

TEI reference:
 - `<add>` element: https://tei-c.org/release/doc/tei-p5-doc/en/html/ref-add.html


### Abbreviations

```
aut combustionem statim ac egredietur <choice><abbr><g ref="#acircum">a</g></abbr><expan>a<ex>ut</ex></expan></choice> radijs
```

&c. > et cetera

```
mine Adonay <choice><abbr><g ref="#et">et</g>c.</abbr><expan><ex>et</ex> c.<ex>etera</ex></expan></choice> ut in 2. Libro.
```

TEI references:
- `<choice>` element: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-choice.html
- `<expan>` element: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-expan.html
- `<abbr>` element: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-abbr.html


### Emphasis

```
nerabilia signa: <hi rend="emphasis">Tau</hi>. Et inter primum et se
```

TEI references:
- `<hi>` element: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-hi.html
- `@rend` attribute: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-att.global.rendition.html

---

## To do
- index of book 1
- additions and deletions? see example correction UTQUE > USQUE on folio 4r
- see comments inline
