# HTML technikos

HTML programavimas ;D Juokas juokais, bet iš tiesų, net ir HTML'as turi visokių papildomų niuansų, kuriuos reikėtų žinoti. Pasinaudojus įvairiomis technikomis galima gan ženkliai optimizuoti puslapio krovimo greitį. Tad ir pakalbėkime apie tokius triukus:

### Video

Norint puslapyje įdėti automatiškai grojantį video, kas dažnu atveju daroma, vietoj seniau naudotinų .gif'ų, galima naudoti HTML5 specifikacijoje aprašytą &lt;video&gt; elementą su papildomais parametrais, kaip `autoplay muted loop` . Kad video būtų automatiškai grojamas ir ant mobiliųjų Apple įrenginių, video elementui būtina uždėti ir papildomą `playsinline` parametrą:

```markup
<video autoplay muted loop playsinline>
    <source src="one-does-not-simply.webm" type="video/webm">
    <source src="one-does-not-simply.mp4" type="video/mp4">
</video>
```

Jeigu video neturi groti automatiškai ir turėtų būti rodomas tik po naudotojo inicijavimo - derėtų ant video elemento nurodyti `preload="none"` parametrą, kuris nurodo, jog nereikia jo iš anksto siųsti. Taipogi tokiu atveju video galima paslėpti po paveikslėliu su parametru `poster`. Tik paspaudus ant jo bus pradedamas krauti ir rodyti video:

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

Pagal šį pavyzdį standartiškai loadinamas 800px pločio paveikslėlis, nebent žiūrima ant mažesnio pločio telefono ekrano. Galima sakyti, šis būdas apjungia &lt;img&gt; elementrą su min-width, max-width css taisyklėmis, pagal kurias galima užkrauti tinkamo dydžio variantą.

#### Kokybė

Antras optimizavimo metodas po dydžio yra paveikslėlio kokybės optimizavimas. Tai dažniausiai daroma kompresijos pagalba pasinaudojant tokius įrankius, kaip kad "Export to web" img redaktoriuose, [https://squoosh.app](https://squoosh.app), [https://tinypng.com](https://tinypng.com/) ir kitais. Dažnu atveju paveikslėliui galima nustatyti pvz 85% kokybės lygį: matomo tinklapyje paveikslėlio kokybė pasikeičia beveik nepastebimai, tačiau paties paveikslėlio svoris gali sumažėti gan ženkliai, pvz. 30-50%. 

Be kompresijos taipogi galima naudoti modernesnius paveikslėlių formatus, pvz .webp. Problema su šiuo formatu yra, kad jo nerodo [Safari ir IE](https://caniuse.com/#search=webp). Apeiti šią problemą galima vietoj &lt;img&gt; elemento naudojant HTML5 &lt;picture&gt; elementą:

```markup
<picture>
  <source type="image/webp" srcset="pyramid.webp"> 
  <img src="pyramid.png" alt="regular pyramid built from four equilateral triangles">
</picture>
```

Naršyklės, kurios palaiko source nurodytą formatą į img src įstatys pirmą tinkamą formatą, o jei nepalaikomas nei vienas - bus kraunamas tiesiog standartinis &lt;img&gt;. Lygiai tas pats principas galioja video elemente, kur vietoj .mp4 derėtų naudoti .webm.

Šis &lt;picture&gt; elementas taipogi gali naudoti responsive img su prieš tai aprašytais `srcset` ar `sizes` parametrais.

Taipogi su &lt;picture&gt; elementu galima atlikti ir [art direction](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images#Art_direction) - principas, kai mažesniuose ekranuose norime rodyti ne tik mažesnę to paties paveikslėlio versiją, tačiau jis turi būti ir visiškai kitokio aspect ratio. Pvz desktop'e naudojama plati horizontali nuotrauka, kurioje pagrindinis objektas centre, tačiau rodant mobiliuose įrenginiuose ją apkerpame, jog pagrindinis fokusas būtų į centrinį objektą: 

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

Tačiau panašu, kad sulauksime ir native lazy load funkcionalumo. Paruoštos specifikacijos dar nėra, bet Chrome jau nuo 76 versijos turi [native palaikymą](https://web.dev/native-lazy-loading). Naudojimo principas tampa dar paprastesniu: užtenka ant paveikslėlio elemento, kuris yra už matomumo ribos, uždėti papildomą `loading="lazy"` parametrą:

```markup
<img src="image.png" loading="lazy" alt="…" width="200" height="200">
```

Naršyklės, kurios loading parametro dar nepalaiko - kraus paveikslėlį, kaip įprasta. Galima šiuos du metodus apjungti ir tokiu atveju lazy loadinti paveikslėlius nepriklausomai nuo naršyklės:

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

 `if ('loading' in HTMLImageElement.prototype) {` patikrina ar naršyklė palaiko loading parametrą ir jei taip - pakeičia visų paveikslėlių su šiuo parametru `data-src` į tiesiog `src` , kitu atveju dinamiškai užkraunama lazysizes biblioteka. Alternatyva galėtų būti, kai tiesiog į tinklapį įtraukiama lazysizes biblioteka ir papildomas jos [plugin'as](https://github.com/aFarkas/lazysizes/tree/gh-pages/plugins/native-loading), kuris šį darbą atlieka automatiškai ir tokiu atveju aukščiau esamo kodo naudoti nebereikia.

