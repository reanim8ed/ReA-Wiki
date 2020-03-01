# Tools

## Code snippet manager

Naudingi išsisaugoti kodo fragmentai turi gulėti cloud'e, jog būtų galima juos pasiekti dirbant iš bet kurio kompiuterio. Šiai paskirčiai puikiai tinka pastebin principu veikiantis [Github Gist](https://gist.github.com/).   
Pradžioje saugojimą atlikdavau tiesiogiai, o šį servisą galima integruoti tiesiai į IDE ar teksto redaktorių ir kodo pavyzdžius pasiimti net neišeinant iš jų. Tačiau archyvui pradėjus augti greitai pajutau, kad visas šis flow nepatogus, labai apribotos organizuotumo galimybės, kas prailgina paiešką. Kokia nauda tuomet saugotis kodą, jei prireikus ko gero išgooglinti būtų galima jį ir greičiau. Tad atsirado kliento poreikis.

Nenoriu naudotis servisais, kurie siūlo tik lokalų kodo saugojimą ar bando kišti savo cloudinius sprendimus ir juo labiau tais, kurie turi subscription modelį \([Cacher](https://www.cacher.io/), [Snippet Manager](https://snippetmanager.io/), [Snipit](https://snipit.io/)\).

Mac'ai tuo tarpu turi gan puikius [Snippet Lab](https://www.renfei.org/snippets-lab/), [Quiver](http://happenapps.com/#quiver) ar [SnipperApp](https://snipper.app/). Tad ieškau būtent tokių ir Win alternatyvų. 

* [Gisto](https://www.gistoapp.com/) - veikia, tačiau ne itin patinka interface'as
* [Lepton](https://hackjutsu.com/Lepton/) - pradėjau naudoti ir mano reikmėm veikia pakankamai puikiai, tačiau yra keli erzinantys apribojimai, pvz sidebar'e esančių sekcijų negalima stumdyti/praplėsti, taipogi nėra galimybės atlikti paieškos current lange.
* [Boostnote](https://boostnote.io/) - atrodo puikiai, taipogi yra web versija, plačios customize galimybės ir planuojami net ir mobile apps'ai. Tačiau šiuo metu neturi tiesioginės integracijos su Gist ir galima kodą laikyti lokaliai arba jų cloud'e, kas yra deal breaker. Tačiau yra bent šioks toks workaround'as - pasirinkus saugojimą lokaliai, galima nusirodyti Dropbox folderį ir sinchronizuotis tarp skirtingų kompiuterių tokiu būdu.
* [SnipAway](https://snipaway.futureglobe.de/) - plačios customize galimybės, tačiau tiesioginės integracijos su Gist neturi. Galima taipogi saugotis per kitus third party cloud'us.

## Alfred alternatives

Android telefonai turi Tasker'į - itin galingą automatizavimo įrankį, kuris telefone iš esmės sugeba daryti viską ką tik moka pats telefonas. Nors nėra itin intuityvus, bet galimybės visą tai tiesiog atperka. Ir jis neturi realaus atitikmens iOS pasaulyje \(iOS turi shortcuts ir tai žingsnis tinkama linkme, tačiau Tasker'iui neprilygsta\). 

Lygiai taip Mac'ai turi savo killer programą, dėl kurios galima pavydėti - [Alfred](https://www.alfredapp.com/). Jau kurį laiką ieškau Win alternatyvos ir dauguma nebepalaikomos arba funkcionalumas daugiausiai susiveda tik į program launcher'į, o tam iš esmės užtenka win mygtuku iškviečiamo Windows start'o ir atskiros programos tam nereikia. Toli gražu iki pagal savo poreikius nesunkiai pritaikomo Alfred'o universalumo, kuris su workflow funkcionalumu, shell integracija ir hotkeys tampa itin universalus ir galingas. 

Šiuo metu naudoju Cerebro, kurio kai kurie funkcionalumai, kaip Translate, valiutų konvertavimas ar maps'ai yra palūžę, tačiau vis dar naudingas dėl instant Google, Wiki, StackOverflow search'o, integracijos su Giphy, Youtube, PhpStorm, bei clipboard istorijos. Tačiau galbūt grįšiu atgal prie Wox, kuris nors oficialiai nebepalaikomas, turi [fork'ą](https://github.com/jjw24/Wox/releases), prie kurio aktyviai dirbama.

* [Wox](http://www.wox.one/)
* [Cerebro](https://cerebroapp.com/)
* [Keypirinha](https://keypirinha.com/)
* [Launchy](http://www.launchy.net/)

## Wikis

Ieškau self-hosted alternatyvų Gitbook'ui. Noriu, kad softas būtinai turėtų hierarchinę struktūrą su markdown palaikymu ir galėčiau pushinti į git'ą. Kelios rastos alternatyvos:

* [TiddlyWiki ](https://tiddlywiki.com/)- konceptualiai labai įdomus sprendimas, kur kiekvienas notes'as yra tarsi kortelė \(vadinama tiddler'iu\) ir kur kiekvienas atidarytas notes'as ir lieka atidarytas naviguojant tarp jų. Turėtų būti patogu daryti tokiem mindmap'ams. Nepatinka senstelėjęs dizainas \(galima kiek pagerinti situaciją su [Material ](http://demo.santosa.family/)dizainu\) ir tai, kad visas turinys saugosi viename faile.
* [Trilium Notes](https://github.com/zadam/trilium) - atrodo išties neblogai, tačiau praktiškai neturi markdown palaikymo bei skirta tik personal naudojimui.
* [MkDocs ](https://www.mkdocs.org/#mkdocs)su [Material tema](https://squidfunk.github.io/mkdocs-material/) / [MDwiki](http://dynalon.github.io/mdwiki/#!index.md) - iš principo labiausiai artimi Gitbook'ui selfhosted sprendimai
* [Wiki.js](https://wiki.js.org/) / [docsify](https://docsify.js.org/#/?id=docsify) - šiuolaikiškesnės JS alternatyvos. Veikia maloniai, tačiau kadangi yra runtime-driven tai praktiškai nėra SEO.
* [Vuepress](https://vuepress.vuejs.org/) - Vue pagrindu veikianti Wiki. Ateityje potencialiai galėčiau pereiti dėl greičio. Tačiau kol kas ne, nes vis dar nėra content meniu, paieška ieško tik pavadinimuose.
* [BookStack ](https://www.bookstackapp.com)- knygos, skyrių ir puslapių principu organizuotas laravel'inis CMS'as. Turi build-in redaktorių ir file manager'į, tačiau UI kiek per daug atima iš turinio bei content'as jau saugojamas duombazėje

Kelios ne self-hosted alternatyvos:

* [Slite](https://slite.com/features)
* [Tettra](https://tettra.co/)
* [Notion](https://notion.so)

## Notes

* [Inkdrop ](https://inkdrop.app/)- nors pozicionuojamas daugiausiai, kaip Markdown editorius, tačiau iš esmės yra pigesnė \($5 vs $8\) Evernote alternatyva. Panašus layout'as su notebook'ai ir tag'ais, sync, web cliperiu ir multiplatformiškumu. Labai gerai išdirbtas, geras MacOS'iškas UI, malonus naudoti, tačiau visai neturi free plano.
* [Standart Notes](https://standardnotes.org/) yra artimiausia Evernote alternatyva, kurią so far pavyko rasti. Nemokamas, cross-platform'inis, labai panašus failų organizavimas. Jei reikia daugiau laisvės, nei suteikia Google Keep - manau vienas geresnių pasirinkimų.
* [Notion ](https://www.notion.so)- multiplatforminė ir sąlyginai nemokama Evernote alternatyva, turinti visai neblogų pranašumų. Pvz.: palaiko DB stiliaus lenteles, Trello stiliaus kanban bei turi markdown support'ą. Viena pagrindinių paskirčių kaip galiu panaudoti - greitas research draft'as, pvz kelionių planavimai. Tačiau startuoja kiek lėtai ir feature overload'as kiek apsunkina naudojimą, nėra itin intuityvus. 
* [GGather](https://ggather.com/all) - programavimui skirtų įrankių, bibliotekų, resursų ir bookmarksų saugykla. Seniau naudojau Google Keeps, bet buvo labai nepatogu, nes viskas susiliedavo į didelę betvarkę ir būdavo sunku kažką rasti.

## Markdown

* [Caret](https://caret.io/) - visiškai minimalistinis lokalus Markdown editorius, tačiau kuris turi viską ko reikia tokiam produktui. Savo paskirčiai - puikus, tačiau Notion laimi, nes turi sync.
* [Notable ](https://github.com/notable/notable)- kokybiškas local Markdown editorius išlaikantis hierarchinę sistemą
* [Typora](https://typora.io/) - kaip markdown editorius, turi nemažai patogių papildomų funkcijų



