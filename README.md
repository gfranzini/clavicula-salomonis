# Clavicula Salomonis

Semi-diplomatic TEI XML transcription of [Ms. Codex 1673](http://dla.library.upenn.edu/dla/medren/detail.html?id=MEDREN_9962943583503681).
Transcribed for the [_Verba Bestiae_](https://github.com/CIRCSE/VerbaBestiae) project. 


**Comments in the transcription file need addressing!**


## Encoding criteria

- It's not always 100% clear whether the first letter of a word is in capitals. I try to maintain capitalisation in the transcription.
- I remove the last line of one folio if repeated on the next folio.

 

### Encoding Check-list

- line numbers
- paragraphs
- word breaks
- abbreviations
- emphasis
- special characters
- ligatures
- additions and deletions  



## Encoding examples


### Structural division

```
<body>        
    <div type="book" n="1"> <!--BOOK-->
        <div type="chapter" n="1"> <!--CHAPTER-->
            <pb n="1r" /> <!--PAGE/FOLIO-->
                <head>Caput 1...</head> <!--TITLE-->
                <p> <!--PARAGRAPH-->                    
                    <lb n="1"/> <!--LINE-->
                    <lb n="2"/>
                    ...
                </p>
        </div>
    </div>
</body>
```


### Word breaks

```
<lb n="1"/>Initium nostrae clavis inquit Salomon filius <w part="I">Da</w>
<lb n="2"/><w part="F">vid</w> Regis Israel, est Deum timere, et adorare, cum
```

TEI reference:
* `<w>` element: https://tei-c.org/release/doc/tei-p5-doc/en/html/ref-w.html
* `@part` attribute: https://tei-c.org/release/doc/tei-p5-doc/en/html/ref-att.fragmentable.html

### V vs. U
SISTEMARE RETRO-ATTIVAMENTE.

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
<lb n="133"/>aut combustionem statim ac egredietur <choice><abbr><g ref="#acircum">a</g></abbr><expan>a<ex>ut</ex></expan></choice> radijs
```

&c. > et cetera

```
<lb n="27"/>mine Adonay <choice><abbr><g ref="#et">et</g>c.</abbr><expan><ex>et</ex> c.<ex>etera</ex></expan></choice> ut in 2. Libro.
```

TEI references:
- `<choice>` element: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-choice.html
- `<expan>` element: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-expan.html
- `<abbr>` element: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-abbr.html


### Emphasis

```
<lb n="96"/>nerabilia signa: <hi rend="emphasis">Tau</hi>. Et inter primum et se
```

TEI references:
- `<hi>` element: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-hi.html
- `@rend` attribute: https://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-att.global.rendition.html

---

## To do
- Finish encoding index of book 1
- line break in chapter headers?
- additions and deletions: mark them or not? see example correction UTQUE > USQUE on folio 4r
