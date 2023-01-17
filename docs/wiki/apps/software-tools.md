# Software tools

- tags: #software  #tools
---

## File sync
* [Syncthing](https://syncthing.net/) - tiesioginis failų sinchronizavimas tarp dviejų ar daugiau kompiuterių, kaip alternatyva nenaudoti cloud storage.
* [LockHunter ](https://www.lockhunter.com/index.htm)- tais atvejais, kai norima ištrinti failą, tačiau jį bala žino kas naudoja ir to padaryti tiesiog neleidžia. Kiek platesnė Unlocker alternatyva, nes sugeba ne tik atrakinti failą jo ištrynimui, tačiau ir parodo procesus, kurie šį failą naudoja.
* [Cryptomator](https://cryptomator.org/) - saugus failų saugojimas kompiuteryje ar cloud servisuose juos užkoduojant.

## Privacy tools

* [https://www.privacyguides.org/tools/](https://www.privacyguides.org/tools/)
* [https://www.privacytools.io/](https://www.privacytools.io/)
*  [LibreWolf](https://librewolf.net/) - į privacy orientuotas Firefox fork'as, kuris pašalina viską, kas susiję su Mozilla kompanija, t.y. ta pati paskirtis, kaip Chromium'as Chrome atžvilgiu.

### Browsers

* [https://adguard-dns.io/en/welcome.html](https://adguard-dns.io/en/welcome.html) - beta versijoje esanti NextDNS alternatyva. Pastarasis yra gan gerai establishintas ir veikia tikrai neblogai, tačiau Adguard turi gerą reputacija ir yra kur kas didesni ir populiaresni, tad visai įdomu pamatyti ar konkurencija duos vaisių.
* [uBlacklist](https://iorate.github.io/ublacklist/docs) - domeno blokavimas iš paieškos rezultatų
* [SearchFilters](https://github.com/quenhus/uBlock-Origin-dev-filter) - uBlock Origin filtras, skirtas iš paieškos rezultatų išfiltruoti useless StackOverflow ir Github copycat puslapius.

### Anonymous Email Forwarding

Kai Firefox pristatė savo Relay servisą, kuris forwardina el. laiškus panašiu principu, kaip tai daro Apple su "Sign In With Apple" opcija, kuri leidžia vartotojui paslėpti savo tikrąjį el.pašto adreso nuo paslaugos tiekėjo, tokio pobūdžio servisas mane visai sudomino. Tai suteikia galimybę kiekvienoje svetainėje naudoti unikalų el. pašto adresą ir kai pradedamas gauti spam'as, galima tiksliai identifikuoti iš kur buvo nuleakinti duomenys ir atjungti siuntimą vos vieno mygtuko paspaudimu. O taipogi tai dar viena papildoma saugumo priemonė, nes nutekėjus prisijungimo duomenims, niekur kitur jų pernaudoti nepavyktų, net jei slaptažodis ir būtų naudojamas tas pats.

Tačiau šis servisas turi 2 ryškius minusus. Pirmiausia, tai nemokamoje versijoje galima susikurti vos tik 5 alias, tad iš esmės juos reikėtų pernaudoti, o tai iš esmės panaikina tokio serviso vieną iš esminių privalumų. Tai būtų galima išspręsti su premium versija, kuri kainuoja vos 1€/mėn. Tačiau čia ir antrasis minusas - tai Mozilla servisas, kurių comitmentu ir projekto ilgaamžiškumu galima sudvejoti. Yra gan didelė tikimybė, jog po poros metų, jie shiftins savo fokusą ir sugalvos servisą uždaryti (geras to pvz buvo jų Send servisas, gyvavęs vos metus).

Tad teko pasidomėti alternatyvomis:

* [https://anonaddy.com](https://anonaddy.com) - nemokami alias, tačiau ribotas bandwidth
* [https://simplelogin.io](https://simplelogin.io) - neribotas srautas, tačiau nemokamas tier'as turi tik 15 alias apribojimą

Anonaddy - geresnis pasirinkimas, jei norima naudoti nemokamai, o jei ir mokama - jis yra pigesnis. Tačiau SimpleLogin labiau išdirbtas bei nukreipus savo domain'ą, turi catch-all funkcionalumą, kai pašto dėžutės alias susikuria automatiškai, kai tik į tą domeną pirmą kartą atsiunčiamas laiškas, kas yra labai neat funkcija, nes netrukdo registracijos flow ir galima random alias susigalvoti tiesiog bepildant registracijos formą.

## Screenshots

Win:

* absoliutus favoritas: [ShareX](https://getsharex.com)

Mac:

* Daugiausiai naudoju nemokamą [Zappy](https://zapier.com/zappy)
* Native: command + shift + 4
* [Cleanshot X](https://cleanshot.com) - daugiausiai features'ų, tačiau mokamas
* [Shottr](https://shottr.cc) - turi Text recognition
* [Xnip](https://xnipapp.com)

## Code snippet manager

Naudingi išsisaugoti kodo fragmentai turi gulėti cloude, jog būtų galima juos pasiekti dirbant iš bet kurio kompiuterio. Vienas iš variantų - naudoti snippet managerį, kuris saugotų į markdown failus, tokiu atveju galima juos saugoti į dropbox direktoriją.

Tačiau daug labiau nice, kai snippet manageris turi [Github Gist](https://gist.github.com) palaikymą ir gali sinchronizuotis tiesiai į ten.

Pradžioje saugojimą atlikdavau tiesiogiai, o šį servisą galima integruoti tiesiai į IDE ar teksto redaktorių ir kodo pavyzdžius pasiimti net neišeinant iš jų. Tačiau archyvui pradėjus augti greitai pajutau, kad visas šis flow nepatogus, labai apribotos organizuotumo galimybės, kas prailgina paiešką. Kokia nauda tuomet saugotis kodą, jei prireikus ko gero išgooglinti būtų galima jį ir greičiau. Tad atsirado client poreikis.

Nenoriu naudotis servisais, kurie siūlo savo cloudinius sprendimus ir juo labiau tais, kurie turi subscription modelį ([Cacher](https://www.cacher.io), [Snippet Manager](https://snippetmanager.io), [Snipit](https://snipit.io)).

Tad labiausiai priimtini variantai:

Mac: [Snippet Lab](https://www.renfei.org/snippets-lab/), [Quiver](http://happenapps.com/#quiver), [SnipperApp](https://snipper.app), [masscode](https://masscode.io), [codespace](https://codespace.app).

Windows:

* [Boostnote](https://boostnote.io) - programos rewrite'as, kuris atrodo visai neblogai. Patinka jog pakankamai aktyviai prie jo dirbama, taipogi yra web versija, plačios customize galimybės ir planuojami net ir mobile apps'ai. Tačiau šiuo metu neturi tiesioginės integracijos su Gist ir galima kodą laikyti lokaliai.
* [SnipAway](https://snipaway.futureglobe.de) - plačios customize galimybės, turi feature'ą įtraukti internetinius puslapius tiesiogiai į redaktorių, tačiau tiesioginės integracijos su Gist neturi. Galima nebent lygiai taip pat saugotis per kitus third party cloud'us.
* [Lepton](https://hackjutsu.com/Lepton/) - kol kas tinka labiausiai. Sinchronizuojasi neblogai, organizacija vykdoma tag'ais, bei automatinis skirstymas pagal file extension'us. Note'us darausi daugiausiai su markdown'u ir patinka jog edit ir preview yra atskiri režimai. Yra vos keli šiek tiek erzinantys apribojimai, pvz sidebare esančių sekcijų negalima praplėsti, tad nesimato pilno tag list'o, taipogi paieška apribota tik title'uose ir failų pavadinimuose, ieškoti turinio galimybės nėra. Na ir tai yra electron appsas, tad greitis nedžiugina.

Daugiau: [https://www.slant.co/topics/7247/\~code-snippets-manager](https://www.slant.co/topics/7247/\~code-snippets-manager)

## Alfred alternatives

* [Wox](http://www.wox.one)
* [Cerebro](https://cerebroapp.com)
* [Keypirinha](https://keypirinha.com)
* [Launchy](http://www.launchy.net)

Android telefonai turi Tasker'į - itin galingą automatizavimo įrankį, kuris iš esmės gali automatizuoti bet kurią telefone pasiekiamą funkciją. Nors nėra itin intuityvus, bet suteikiamos galimybės visą tai tiesiog atperka. iOS barikadų pusėje lygiaverčio atitikmens nėra, nes nors Shortcuts pagalba ir galima susikurti išties naudingų funkcijų, tačiau dėl OS sukuriamų apribojimų, geležies valdymo galimybėmis šis įrankis Tasker'iui išties neprilygsta.

Lygiai taip Mac'ai turi savo killer programą, dėl kurios galima pavydėti - [Alfred](https://www.alfredapp.com). Jau kurį laiką ieškau adekvačios Win alternatyvos, tačiau dauguma yra užleistos arba funkcionalumas gan ribotas ir susiveda tik į programų paleidimą ar kokį skaičiuotuvą, o tokioms funkcijos iš esmės užtenka win mygtuku iškviečiamo Windows start'o ir ten esančios paieškos ir atskiros programos tam diegti nereikia. Tokiuose įrankiuose yra galimybė bazinį funkcionalumą praplėsti įvairiais įskiepiais, tačiau prie jų nėra aktyviai dirbama ir didelė dalis arba nebeveikia arba veikia labai nestabiliai. Tad tai toli gražu iki lankstaus Alfred'o, kuris su workflow funkcionalumu, shell integracija ir hotkeys tampa itin universalus ir galingas.

Tarp išbandytų man labiausiai tiko Cerebro, kurio Translate, valiutų konvertavimas ar maps'ai yra sulūžę, tačiau jis vis vien naudingas dėl instant Google, Wiki, StackOverflow search'o, integracijos su Giphy, Youtube, PhpStorm, bei clipboard istorijos.

Tačiau visai nesenai pasirodė daug žadančios naujienos ir iš paties Microsoft. Komanda žmonių gan aktyviai dirba prie [PowerToys ](https://github.com/microsoft/PowerToys)projekto - tai įrankių rinkinys, siūlantis praplėsti standartines Windows galimybes. Pvz įdiegiamas .svg, .md failų preview'as tiesiog exploreryje, Image Resizer integracija, FancyZones - windows layout'ų manageris, leidžiantis ekraną išdalinti į dedikuotas zonas ir kita. Vienas iš naujų šio rinkinio įrankių - Run. Tai program launcher'is, prie kurio kūrimo pasirodo prisideda to paties Wox kūrėjai. Pradžioje funkcionalumas gan limituotas, tačiau įrankis turės įskiepių palaikymą, tad aplink jį ko gero netruks susikurti entuziastų bendruomenė ir tuomet jau sky is the limit. Susidiegiau ir su nekantrumu laukiu kokia linkme visą tai išjudės.

## Wikis

Ieškau self-hosted alternatyvų Gitbook'ui. Noriu, kad softas būtinai turėtų hierarchinę struktūrą su markdown palaikymu ir galėčiau pushinti į git'ą. Kelios rastos alternatyvos:

* [TiddlyWiki ](https://tiddlywiki.com)- konceptualiai labai įdomus sprendimas, kur kiekvienas notes'as yra tarsi kortelė (vadinama tiddler'iu) ir kur kiekvienas atidarytas notes'as ir lieka atidarytas naviguojant tarp jų. Turėtų būti patogu daryti tokiem mindmap'ams. Nepatinka senstelėjęs dizainas (galima kiek pagerinti situaciją su [Material ](http://demo.santosa.family)dizainu) ir tai, kad visas turinys saugosi viename faile.
* [Trilium Notes](https://github.com/zadam/trilium) - atrodo išties neblogai, tačiau praktiškai neturi markdown palaikymo bei skirta tik personal naudojimui.
* [MkDocs ](https://www.mkdocs.org/#mkdocs)su [Material tema](https://squidfunk.github.io/mkdocs-material/) / [MDwiki](http://dynalon.github.io/mdwiki/#!index.md) - iš principo labiausiai artimi Gitbook'ui selfhosted sprendimai
* [Wiki.js](https://wiki.js.org) / [docsify](https://docsify.js.org/#/?id=docsify) - šiuolaikiškesnės JS alternatyvos. Veikia maloniai, tačiau kadangi yra runtime-driven tai praktiškai nėra SEO.
* [Vuepress](https://vuepress.vuejs.org) - Vue pagrindu veikianti Wiki. Ateityje potencialiai galėčiau pereiti dėl greičio. Tačiau kol kas ne, nes vis dar nėra content meniu, paieška ieško tik pavadinimuose.
* [BookStack ](https://www.bookstackapp.com)- knygos, skyrių ir puslapių principu organizuotas laravel'inis CMS'as. Turi build-in redaktorių ir file manager'į, tačiau UI kiek per daug atima iš turinio bei content'as jau saugojamas duombazėje

Kelios ne self-hosted alternatyvos:

* [Slite](https://slite.com/features)
* [Tettra](https://tettra.co)
* [Notion](https://notion.so)

## Note taking

* [Inkdrop ](https://inkdrop.app)- nors pozicionuojamas daugiausiai, kaip Markdown editorius, tačiau iš esmės yra pigesnė ($5 vs $8) Evernote alternatyva. Panašus layout'as su notebook'ai ir tag'ais, sync, web cliperiu ir multiplatformiškumu. Labai gerai išdirbtas, geras MacOS'iškas UI, malonus naudoti, tačiau visai neturi free plano.
* [Simple Note](https://simplenote.com/) - nemokamas ir multiplatforminis appsas notų saugojimui, su Markdown supportu
* [Standart Notes](https://standardnotes.org) yra artimiausia Evernote alternatyva, kurią so far pavyko rasti. Nemokamas, cross-platform'inis, labai panašus failų organizavimas. Jei reikia daugiau laisvės, nei suteikia Google Keep - manau vienas geresnių pasirinkimų.
	* [Awesome Standart Notes](https://github.com/jonhadfield/awesome-standard-notes) - A curated list of tools and information relating to Standard Notes
* [Notion ](https://www.notion.so)- multiplatforminė ir sąlyginai nemokama Evernote alternatyva, turinti visai neblogų pranašumų. Pvz.: palaiko DB stiliaus lenteles, Trello stiliaus kanban bei turi markdown support'ą. Viena pagrindinių paskirčių kaip galiu panaudoti - greitas research draft'as, pvz kelionių planavimai. Tačiau startuoja kiek lėtai ir feature overload'as kiek apsunkina naudojimą, nėra itin intuityvus.
	* [Craft](https://www.craft.do/solutions/individuals) - Notion alternative

## Bookmarking tools

Chrome bookmarks'ų galimybės išties labai apribotos ir iš esmės be katalogų kūrimo funkcionalumas ties tuo ir pasibaigia. Google buvo išleidusi oficialų extension'ą Bookmark Manager, kuris prideda papildomo funkcionalumo, tačiau kaip ir reikia tikėtis - jo vystymas jau nutrauktas ir extension'as pašalintas iš web store. Visokie third party extension'ai dažniausiai nelabai tinka, nes bookmarks'us turėčiau pasiekti ir iš smartphone'o.

Taigi išsisaugoti nuorodoms iki šiol naudojau Google Keep ir Pocket kombinaciją. Į Pocket keliauja Plan To Read straipsniai ar naudingos, šiam momentui aktualios nuorodos. Į Keep jos perkeliamos ilgalaikiam saugojimui. Pvz planuojamos skaityti knygos ar naudingi programavimo įrankiai. Tačiau Keep paskirtis tam nelabai tinkama, o ir turint dvi atskiras saugykas, paieška tampa neefektyvi, tad toks organizavimas nelabai tenkina.

* [GGather](https://ggather.com/all) - įkvepia tituliniame pateikti užtikrinimai apie tai, jog produktas specialiai kurtas su minimaliomis išlaidomis, jog nereikėtų desperatiškai ieškoti investuotojų ar visokiais shady metodais bandyti monetizuoti vartotojus. Tokius kūrėjus norisi palaikyti. Minusai: bookmarksas atidaromas ne iškarto, o pirma atidaromas detalus jo langas, o tik tada galima atidaryti jį naujame tab'e. Taipogi naudojantis nemokama versija yra tik 2 list stiliaus atvaizdavimo būdai, kurie nėra itin patogūs. Kol kas vis dar nėra native apps'ų, tad pasiekti galima tik per webinę versiją. Manau reikės prachekinti ateityje, bet šiai dienai nėra itin atitinkantis mano lūkesčių.
* [Pinboard ](https://pinboard.in)- nebrangus (11$ metams, 25 norint turėti turinio cache'avimą ir full text paiešką), jokių reklamų ir jokio trackinimo. Programuotojų mylimas no bullshit servisas su puikiu funkcionalumu, tačiau old schooliniu dizainu (kai kuriems tai yra labiau pliusas). Bookmarksai iš esmės atvaizduojami panašiai, kaip Google paieškos rezultatai. Naudojantis mac'u, galima pasidaryti gan puikų flow su Alfred. Pagrindinis minusas - HackerNews teko skaityti, kad developeris yra tik vienas pats ir jis yra praktiškai apleidęs projektą, skiria jam labai mažai dėmesio, pvz archyvavimo funkcija labai dažnai nulūžta, jis praktiškai neatrašinėja į supporto laiškus.
* [Raindrop](https://raindrop.io) - komandos iš Sankt Peterburgo kūrinys. Labai intuityvus ir responsive įrankis, turintis puikų įskiepį, kurį galima nusistatyti naudoti kaip web clipperį arba kaip mini app'są, iš kurios galima greitai ieškoti ir pasiekti bet kurį bookmarks'ą. Nested kategorijos pasiekamos tik mokomoje versijoje, tačiau antrą lygį kataloge galima įgyvendinti naudojantis tiesiog tag'ais, kurie patogiai atvaizduojami atsidarius kategoriją. Taipogi susimokėjus vienam mėnesiui galima pasidaryti visą savo nested kategorijų struktūrą ir nutraukus prenumeratą galima ja naudotis ir toliau. Yra platus ikonų support'as, mobilūs apps'ai, dark mode, 4 atvaizdavimo būdai, automatiniai tag suggestion'ai, įskiepis visiems pagrindiniams browseriams. Mokomoje versijoje prisideda dublikatų paieška, turinio archyvinis cache'avimas, broken link tikrinimas ir pan. Pagrindiniai minusai: raginimas pereiti į mokamą versiją, ne itin aiškios ateities perspektyvos ir privacy klausimai.
* [Reminiscence ](https://github.com/kanishka-linux/reminiscence)- self hosted sprendimas

## Markdown

* [Caret](https://caret.io) - visiškai minimalistinis lokalus Markdown editorius, tačiau kuris turi viską ko reikia tokiam produktui. Savo paskirčiai - puikus, tačiau Notion laimi, nes turi sync.
* [Notable ](https://github.com/notable/notable)- kokybiškas local Markdown editorius išlaikantis hierarchinę sistemą
* [Typora](https://typora.io) - kaip markdown editorius, turi nemažai patogių papildomų funkcijų
* [Zettlr](https://www.zettlr.com)

## Markdown publishing

- [Publish your Obsidian Notes](https://github.com/jobindjohn/obsidian-publish-mkdocs)
- [Flowershow: A Free & Open Source tool for publishing your Obsidian vaults](https://forum.obsidian.md/t/flowershow-a-free-open-source-tool-for-publishing-your-obsidian-vaults/41966/1)
- [VuePress](https://v2.vuepress.vuejs.org/)
- [Docusaurus](https://docusaurus.io/)