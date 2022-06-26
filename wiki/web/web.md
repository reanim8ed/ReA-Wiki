# Web

### Links

* Šiandieninio interneto būklė: [https://how-i-experience-web-today.com/](https://how-i-experience-web-today.com/)

### Web 3.0

Pastaruoju metu kyla vis daugiau diskusijų apie WEB 3.0. Tai gan abstraktus terminas, tačiau kiek suabsoliutinus: web1 buvo kiek chaotiškas, sudėtingai naviguojamas, tačiau užtat decentralizuotas. Kiekvienas norėdamas skelbti informaciją internete, turėjo būti pasikaustęs nemažu knowhow, ko pasekoje masiniam naudojimui jis buvo techniškai per sudėtingas ir riboto prienamumo.\
web2 viskas susicentralizavo į platformas ir taip užgimė keletas interneto gigantų, kurie turi pilną šių tinklų kontrolę, tačiau tokiu būdu šiomis platformomis galėjo naudotis milijardai žmonių.\
web3 pagal idėją vyktų natūrali evoliucija, kai viskas vėl decentralizuojama, išlaikant teigiamuosius web2 aspektus, kaip sistemų lengvumą naudotis ir randamumą.

Tačiau atidžiau pasinagrinėjus dabartinę web3 rinką, galima pastebėti, kad teiginiai apie decentralizavimą gali būti ne tokie jau ir teisingi: ganėtinai daug statoma aplink kelis dominuojančius API tiekėjus, o natūraliai atsirandantis naujų, praplėstų galimybių poreikis, kurių palaikymo naudojamose krypto technologijose dažnai nebūna - tik dar labiau skatina šiuos API tiekėjus plėstis, pildyti šiuos poreikius savo sprendimais ir taip vis labiau konsoliduojant viską į savo platformas. Tai išesmės vėl gaunasi tas pats web2, tik kitaip.

> _Given the history of why web1 became web2, what seems strange to me about web3 is that technologies like ethereum have been built with many of the same implicit trappings as web1. To make these technologies usable, the space is consolidating around… platforms. Again. People who will run servers for you, and iterate on the new functionality that emerges. Infura, OpenSea, Coinbase, Etherscan._

* [https://moxie.org/2022/01/07/web3-first-impressions.html](https://moxie.org/2022/01/07/web3-first-impressions.html)

### Anonymous Email Forwarding

Kai Firefox pristatė savo Relay servisą, kuris forwardina el. laiškus panašiu principu, kaip tai daro Apple su "Sign In With Apple" opcija, kuri leidžia vartotojui paslėpti savo tikrąjį el.pašto adreso nuo paslaugos tiekėjo, tokio pobūdžio servisas mane visai sudomino. Tai suteikia galimybę kiekvienoje svetainėje naudoti unikalų el. pašto adresą ir kai pradedamas gauti spam'as, galima tiksliai identifikuoti iš kur buvo nuleakinti duomenys ir atjungti siuntimą vos vieno mygtuko paspaudimu. O taipogi tai dar viena papildoma saugumo priemonė, nes nutekėjus prisijungimo duomenims, niekur kitur jų pernaudoti nepavyktų, net jei slaptažodis ir būtų naudojamas tas pats.

Tačiau šis servisas turi 2 ryškius minusus. Pirmiausia, tai nemokamoje versijoje galima susikurti vos tik 5 alias, tad iš esmės juos reikėtų pernaudoti, o tai iš esmės panaikina tokio serviso vieną iš esminių privalumų. Tai būtų galima išspręsti su premium versija, kuri kainuoja vos 1€/mėn. Tačiau čia ir antrasis minusas - tai Mozilla servisas, kurių comitmentu ir projekto ilgaamžiškumu galima sudvejoti. Yra gan didelė tikimybė, jog po poros metų, jie shiftins savo fokusą ir sugalvos servisą uždaryti (geras to pvz buvo jų Send servisas, gyvavęs vos metus).

Tad teko pasidomėti alternatyvomis:

* [https://anonaddy.com](https://anonaddy.com) - nemokami alias, tačiau ribotas bandwidth
* [https://simplelogin.io](https://simplelogin.io) - neribotas srautas, tačiau nemokamas tier'as turi tik 15 alias apribojimą

Anonaddy - geresnis pasirinkimas, jei norima naudoti nemokamai, o jei ir mokama - jis yra pigesnis. Tačiau SimpleLogin labiau išdirbtas bei nukreipus savo domain'ą, turi catch-all funkcionalumą, kai pašto dėžutės alias susikuria automatiškai, kai tik į tą domeną pirmą kartą atsiunčiamas laiškas, kas yra labai neat funkcija, nes netrukdo registracijos flow ir galima random alias susigalvoti tiesiog bepildant registracijos formą.
