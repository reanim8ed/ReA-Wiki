# HTML technikos

HTML programavimas ;D Juokas juokais, bet iš tiesų, net ir HTML'as turi visokių niuansų, kuriuos derėtų žinoti. Pasinaudojus įvairiomis technikomis galima gan ženkliai optimizuoti puslapio krovimo greitį. Tad ir pakalbėkime apie visokius triukus ir taktikas.



### Best practices for images

{% embed url="https://github.com/nucliweb/image-element" %}

### Javascript

Nuo HTM5 specifikacijos išleidimo nebėra privalomybės \<script> elementui nurodinėti`type="text/javascript"` . Pvz naudojantis W3 validatoriumi, jis ant scriptų, kurie turės šitą atributą, rodys warning žinutę. Jei visus scriptus įtraukinėjame patys, tai galima jų įtraukimo sintaksę supaprastinti, tačiau jeigu naudojami third-party moduliai, scriptai ar library, tai tikėtina, jog jie automatiškai įtraukinės scriptus senąja sintakse.

#### Async ir defer

Įprastai jei script'as yra įterptas puslapio viršuje, tai `window.onload` event'as nebūna trigerinamas tol, kol neužbaigiamos šio resurso loadinimas. Dauguma modernių svetainių, kurios kurtos su pagrindiniais frontent frameworkais, remiasi į šį event'ą. Tad dalis UI gali būti nerenderinama, tol kol neužbaigti render-blocking requestai. Būtent dėl šio priežasties Google Lighthouse ar PageSpeed Insights rodys atitinkamą klaidą. Šiai problemai spręsti galima naudoti vieną iš šių dviejų atributų.

Pirmasis, `async` naudojamas asinchroniniam script'o atsisiuntimui. T.y. tol, kol jis bus kraunamas, jis nestabdys likusio tinklapio krovimo ir vos tik scriptas bus parsiųstas - jis iškarto įvykdomas. Paprastas panaudojimo pavyzdys - Google Analytics kodas.

Tuo tarpu `defer` taipogi siunčiamas asinchroniškai, tačiau scripto vykdymas atidėtas iki tol, kol dokumentas baigiamas parsinti. Tad jis daugiausiai reikalingas, kai scriptas yra priklausomas nuo kitų scriptų, pvz kokio jQuery'io.

Tai geroji praktika būtų naudoti `async` visur, kur įmanoma, o kai jis netinka, tada revertintis į `defer`.

### SEO

Linkai turi `rel` atributą, kuris nurodo nuorodos sąryšį su dabartiniu puslapiu. Išviso yra net 14 skirtingų `rel` reikšmių, tačiau dauguma iš jų nėra itin svarbios. Tačiau noriu atkreipti dėmesį į kelias gan svarbesnes:

* `nofollow` - ši reikšmė ko gero yra ir taip neblogai žinoma, jei bent kiek užsiimama SEO optimizacijomis. Iš esmės nurodo, jog nuoroda nėra susijusi su mūsų dabartiniu puslapiu, nėra jo dalis ir SEO įtaka nėra perduodama. Puikiai tinka, kai dedamos nuorodos į partnerių, rėmėjų puslapius, tinklapio kūrėjų nuorodai.
* `noreferrer` - neperduoda nukreipimo informacijos. T.y. statistikoje nesimatys, jog tinklapio lankytojas atėjo iš jūsų puslapio.
* `noopener` - kai naudojamasi `target=_blank` atributu, naujai atidarytas langas `window.opener` pagalba gali visvien pasiekti jį atidariusio [puslapio langą](https://mathiasbynens.github.io/rel-noopener/). Tai yra pavojinga, nes jei nukreipiate į third-party puslapį ir jį buvo įsilaužta, tai naudotojui, kuris paspaudžia ant šios nuorodos įmanoma potencialiai redirectinti jūsų tinklapio tab'ą į visai kitą žalingą URL. `noopener` uždaro duris tokio pobūdžio atakai.

## Elementai

### Video

Norint puslapyje įdėti automatiškai grojantį video, kas dažnu atveju daroma, vietoj seniau naudotinų .gif'ų, galima naudoti HTML5 specifikacijoje aprašytą \<video> elementą su papildomais atributais, kaip `autoplay muted loop` . Kad video būtų automatiškai grojamas ir ant mobiliųjų Apple įrenginių, video elementui būtina uždėti ir papildomą `playsinline` atributą:

```markup
<video autoplay muted loop playsinline>
    <source src="one-does-not-simply.webm" type="video/webm">
    <source src="one-does-not-simply.mp4" type="video/mp4">
</video>
```

Jeigu video neturi groti automatiškai ir turėtų būti rodomas tik po naudotojo inicijavimo - derėtų ant video elemento nurodyti `preload="none"` atributą, kuris nurodo, jog nereikia jo iš anksto siųsti. Taipogi tokiu atveju video galima paslėpti po paveikslėliu su parametru `poster`. Tik paspaudus ant jo bus pradedamas krauti ir rodyti video:

```markup
<video controls preload="none" poster="one-does-not-simply-placeholder.jpg">
  <source src="one-does-not-simply.webm" type="video/webm">
  <source src="one-does-not-simply.mp4" type="video/mp4">
</video>
```

### Picture

Paveikslėliai sudaro didelę dalį šiuolaikinio web'o, tad jiems taipogi reikia skirti dėmesio.

#### Dydis

Pirmiausia reikėtų stengtis visur naudoti paveikslėlius max tokio dydžio, kokie jie yra atvaizduojami interneto puslapyje, t.y. nepalikti darbo naršyklės automatiniam resizinimui, kai pvz straipsnių archyvas kiekvienai straipsnio kortelei krauna 1500x800 dydžio originalias nuotraukas, kai tuo tarpu puslapyje rodomas tik 300x160 dydžio thumbnail'as. Tai ne tik priverčia paveikslėlius ilgiau krautis, nes reikia parsisiųsti daug didesnį duomenų kiekį, tačiau valgo mobiliųjų vartotojų interneto srautą, bei apkrauna CPU darbą. Dėl šios priežasties, jei tinklapyje yra rodomas didelis paveikslėlių kiekis, o nuotraukas yra išties didelės ir tiesiog downsize'intos - scrollinant tokį puslapį - lagina.

Žinoma, jei įdėti max FullHD monitoriuje rodomą paveikslėlių dydį, jis visvien gali būti per didelis žiūrint tablet ar mobile įrenginiuose ir naršyklei vis vien gali tekti paveikslėlį resizinti. Šiai problemai spręsti yra naudojami responsive images:

```markup
<img srcset="elva-fairy-320w.jpg 320w,
             elva-fairy-480w.jpg 480w,
             elva-fairy-800w.jpg 800w"
     sizes="(max-width: 320px) 280px,
            (max-width: 480px) 440px,
            800px"
     src="elva-fairy-800w.jpg" alt="Elva dressed as a fairy">
```

Pagal šį pavyzdį standartiškai loadinamas 800px pločio paveikslėlis, nebent žiūrima ant mažesnio pločio telefono ekrano. Galima sakyti, šis būdas apjungia \<img> elementrą su min-width, max-width css taisyklėmis, pagal kurias galima užkrauti tinkamo dydžio variantą.

#### Kokybė

Antras optimizavimo metodas po dydžio yra paveikslėlio kokybės optimizavimas. Tai dažniausiai daroma kompresijos pagalba pasinaudojant tokius įrankius, kaip kad "Export to web" img redaktoriuose, [https://squoosh.app](https://squoosh.app), [https://tinypng.com](https://tinypng.com) ir kitais. Dažnu atveju paveikslėliui galima nustatyti pvz 85% kokybės lygį: matomo tinklapyje paveikslėlio kokybė pasikeičia beveik nepastebimai, tačiau paties paveikslėlio svoris gali sumažėti gan ženkliai, pvz. 30-50%.

Be kompresijos taipogi galima naudoti modernesnius paveikslėlių formatus, pvz .webp. Problema su šiuo formatu yra, kad jo nerodo [Safari ir IE](https://caniuse.com/#search=webp). Apeiti šią problemą galima vietoj \<img> elemento naudojant HTML5 \<picture> elementą:

```markup
<picture>
  <source type="image/webp" srcset="pyramid.webp"> 
  <img src="pyramid.png" alt="regular pyramid built from four equilateral triangles">
</picture>
```

Naršyklės, kurios palaiko source nurodytą formatą į img src įstatys pirmą tinkamą formatą, o jei nepalaikomas nei vienas - bus kraunamas tiesiog standartinis \<img>. Lygiai tas pats principas galioja video elemente, kur vietoj .mp4 derėtų naudoti .webm.

Šis \<picture> elementas taipogi gali naudoti responsive img su prieš tai aprašytais `srcset` ar `sizes` atributais.

Taipogi su \<picture> elementu galima atlikti ir [art direction](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia\_and\_embedding/Responsive\_images#Art\_direction) - principas, kai mažesniuose ekranuose norime rodyti ne tik mažesnę to paties paveikslėlio versiją, tačiau jis turi būti ir visiškai kitokio aspect ratio. Pvz desktop'e naudojama plati horizontali nuotrauka, kurioje pagrindinis objektas centre, tačiau rodant mobiliuose įrenginiuose ją apkerpame, jog pagrindinis fokusas būtų į centrinį objektą:

```markup
<picture>
  <source media="(max-width: 799px)" srcset="elva-480w-close-portrait.jpg">
  <source media="(min-width: 800px)" srcset="elva-800w.jpg">
  <img src="elva-800w.jpg" alt="Chris standing up holding his daughter Elva">
</picture>
```

#### Krovimas

Krauti paveikslėlius iš karto, kol vartotojas jų dar net nemato, t.y. kol jis yra žemiau fold ribos - nėra tikslinga. Gali būti jog naršyklė parsiuntinės krūvą paveikslėlių, kurie vartotojui taip ir nebus parodyti. Ši problema sprendžiama su "lazy load" funkcionalumu, kai objektai ekrane užkraunami tik tuomet, kai jie tampa matomi naršyklės ekrane. Iki šiol buvo naudojamos JS bibliotekos, kurios pasinaudodamos browserio suteikiamu Intersection Observer API galėjo atlikti šį darbą. Vienas iš tokios bibliotekos pavyzdžių, galėtų būti populiari [lazysizes ](https://github.com/aFarkas/lazysizes)biblioteka. Naudojimas labai paprastas: ant elemento uždedama `class="lazyload"`, o vietoj `src` ar `srcset` naudojami jų atitikmenys, kaip `data-src` ir `data-srcset`

```markup
<img data-src="image.jpg" class="lazyload" />
```

Biblioteka labai universali, veikia ir su responsive img, video ar iframe elementais.

Tačiau panašu, kad sulauksime ir native lazy load funkcionalumo. Paruoštos specifikacijos dar nėra, bet Chrome jau nuo 76 versijos turi [native palaikymą](https://web.dev/native-lazy-loading). Naudojimo principas tampa dar paprastesniu: užtenka ant paveikslėlio elemento, kuris yra už matomumo ribos, uždėti papildomą `loading="lazy"` atributą:

```markup
<img src="image.png" loading="lazy" alt="…" width="200" height="200">
```

Naršyklės, kurios loading atributo dar nepalaiko - kraus paveikslėlį, kaip įprasta.

Galima šiuos du metodus apjungti ir tokiu atveju lazy loadinti paveikslėlius nepriklausomai nuo naršyklės:

```markup
<!-- Let's load this in-viewport image normally -->
<img src="hero.jpg" alt="…">

<!-- Let's lazy-load the rest of images -->
<img data-src="unicorn.jpg" alt="…" loading="lazy" class="lazyload">

<script>
  if ('loading' in HTMLImageElement.prototype) {
    const images = document.querySelectorAll('img[loading="lazy"]');
    images.forEach(img => {
      img.src = img.dataset.src;
    });
  } else {
    // Dynamically import the LazySizes library
    const script = document.createElement('script');
    script.src =
      'https://cdnjs.cloudflare.com/ajax/libs/lazysizes/4.1.8/lazysizes.min.js';
    document.body.appendChild(script);
  }
</script>
```

`if ('loading' in HTMLImageElement.prototype) {` patikrina ar naršyklė palaiko loading atributą ir jei taip - pakeičia visų paveikslėlių su šiuo parametru `data-src` į tiesiog `src` , kitu atveju dinamiškai užkraunama lazysizes biblioteka. Alternatyva galėtų būti, kai tiesiog į tinklapį įtraukiama lazysizes biblioteka ir papildomas jos [plugin'as](https://github.com/aFarkas/lazysizes/tree/gh-pages/plugins/native-loading), kuris šį darbą atlieka automatiškai ir tokiu atveju aukščiau esamo kodo naudoti nebereikia.

#### Placeholders

Programuojant puslapį dažnu atveju prireikia paveikslėlių, kol tuo tarpu tikrų, planuojamų naudoti tinklapyje paveikslėlių ar nuotraukų vis dar neturime, tad reikalingi laikini, t.y. placeholder paveikslėliai. Įprastai tam naudoju vieną iš šių 2 metodų:

* jei noriu iškomunikuoti kokio dydžio paveikslėlis turėtų toje vietoje būti naudojamas, naudoju placehold.it. Pvz: [https://placehold.it/350x250?text=350x250](https://via.placeholder.com/350x250?text=350x250)
* jei norima naudoti tiesiog realius, gražius random paveikslėlius, pvz reprezentuoti slideriui, tai naudoju unsplash. Pvz: [https://source.unsplash.com/random/350x250](https://source.unsplash.com/random/350x250) galima nusirodyti, kad paveikslėlis updatintusi ne kiekvieną kartą pasikreipus, o pvz tik 1 kartą į dieną ar savaitę, taipogi galima atfiltruoti konkrečią temą, pvz: [https://source.unsplash.com/weekly?water](https://source.unsplash.com/weekly?water)

Mažiau profesionalūs, bet užtat daug labiau fun placeholderiai:

* [Fill Murray](http://www.fillmurray.com)
* [PlaceCage](https://www.placecage.com)
* [placekitten](http://placekitten.com)
* [placedog](https://placedog.net)

### Datalist

\<datalist> yra mažiau praktikoje naudojamas elementas, kuris tarsi sujungia input ir select elementus į vieną. T.y. gauname vieną lauką, kuriame galima tiek ir įrašyti savo reikšmę, tiek ir pasirinkti ją iš dropdown'o:

```markup
<label>Your favorite band?
<input list="heavy-bands"
name="band-choice"></label>

<datalist id="heavy-bands">
  <option value="Metallica" />
  <option value="Iron Maiden" />
  <option value="Slayer" />
  <option value="Motörhead" />
  <option value="Megadeth" />
  <option value="Black Sabbath" />
</datalist>
```

### Audio

HTML5 taipogi turi native audio player'į. Tam, kad tinklapyje įterpti garso įrašą, nebūtina naudoti third-party script'us, kurie suteiktų audio player funkcionalumą:

```markup
<audio controls loop preload="none"
  src="deep-house-track.mp3">
</audio>
```

### Details

HTML5.1 specifikacija turi ir native išskleidžiamo accordion'o funkcionalumą:

```markup
<details>
  <summary>Explaining all of the things</summary>
  <p>Some explanation goes here...</p>
</details>
```
