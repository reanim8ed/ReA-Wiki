# Web

* From ex Facebook Software Engineer:\
  The best minds of my generation are thinking about how to make people click ads.
* Šiandieninio interneto būklė: [https://how-i-experience-web-today.com/](https://how-i-experience-web-today.com/)

## Tools

### AdBlock

* [https://adguard-dns.io/en/welcome.html](https://adguard-dns.io/en/welcome.html) - beta versijoje esanti NextDNS alternatyva. Pastarasis yra gan gerai establishintas ir veikia tikrai neblogai, tačiau Adguard turi gerą reputacija ir yra kur kas didesni ir populiaresni, tad visai įdomu pamatyti ar konkurencija duos vaisių.

### Anonymous Email Forwarding

Kai Firefox pristatė savo Relay servisą, kuris forwardina el. laiškus panašiu principu, kaip tai daro Apple su "Sign In With Apple" opcija, kuri leidžia vartotojui paslėpti savo tikrąjį el.pašto adreso nuo paslaugos tiekėjo, tokio pobūdžio servisas mane visai sudomino. Tai suteikia galimybę kiekvienoje svetainėje naudoti unikalų el. pašto adresą ir kai pradedamas gauti spam'as, galima tiksliai identifikuoti iš kur buvo nuleakinti duomenys ir atjungti siuntimą vos vieno mygtuko paspaudimu. O taipogi tai dar viena papildoma saugumo priemonė, nes nutekėjus prisijungimo duomenims, niekur kitur jų pernaudoti nepavyktų, net jei slaptažodis ir būtų naudojamas tas pats.

Tačiau šis servisas turi 2 ryškius minusus. Pirmiausia, tai nemokamoje versijoje galima susikurti vos tik 5 alias, tad iš esmės juos reikėtų pernaudoti, o tai iš esmės panaikina tokio serviso vieną iš esminių privalumų. Tai būtų galima išspręsti su premium versija, kuri kainuoja vos 1€/mėn. Tačiau čia ir antrasis minusas - tai Mozilla servisas, kurių comitmentu ir projekto ilgaamžiškumu galima sudvejoti. Yra gan didelė tikimybė, jog po poros metų, jie shiftins savo fokusą ir sugalvos servisą uždaryti (geras to pvz buvo jų Send servisas, gyvavęs vos metus).

Tad teko pasidomėti alternatyvomis:

* [https://anonaddy.com](https://anonaddy.com) - nemokami alias, tačiau ribotas bandwidth
* [https://simplelogin.io](https://simplelogin.io) - neribotas srautas, tačiau nemokamas tier'as turi tik 15 alias apribojimą

Anonaddy - geresnis pasirinkimas, jei norima naudoti nemokamai, o jei ir mokama - jis yra pigesnis. Tačiau SimpleLogin labiau išdirbtas bei nukreipus savo domain'ą, turi catch-all funkcionalumą, kai pašto dėžutės alias susikuria automatiškai, kai tik į tą domeną pirmą kartą atsiunčiamas laiškas, kas yra labai neat funkcija, nes netrukdo registracijos flow ir galima random alias susigalvoti tiesiog bepildant registracijos formą.

## Fear of Missing Out and Social Media

FOMO is a great motivator of human behavior, and I think a crucial key to understanding social software, and why it works the way it does. Many people have studied the game mechanics that keep people collecting things (points, trophies, check-ins, mayorships, kudos). Others have studied how the neurochemistry that keeps us checking Facebook every five minutes is similar to the neurochemistry fueling addiction. Social media has made us even more aware of the things we are missing out on. You’re home alone, but watching your friends status updates tell of a great party happening somewhere. You are aware of more parties than ever before. And, like gym memberships, adding Bergman movies to your Netflix queue and piling up unread copies of the New Yorker, watching these feeds gives you a sense that you’re participating, not missing out, even when you are.

* [https://caterina.net/2011/03/15/fomo-and-social-media/](https://caterina.net/2011/03/15/fomo-and-social-media/)

## Google+

Vienas iš inžinierių dirbančių prie Google+ [aprašo priežastis](https://onezero.medium.com/why-google-failed-4b9db05b973b), kurios jo nuomone nulėmė kodėl šis socialinis tinklapis nenusisekė.

> When the execs are extremely smart people making 10 times the salary you do, there’s a tendency to give them the benefit of the doubt. Surely they must know what they are doing.

Šis tinklas, kurį aš naudodavau, kurį naudodavo dalelė įdomių mūsų tautiečių ir jį net mėgdavo, turėjo kelias esmines problemas:

* Didelis kiekis neaktyvių account'ų. Kai į tinklą automatiškai įlieti absoliučiai visos egzistuojančios Google paskyros, to pasekoje atsirado "ghost town" problema. Vadovybė tikėjosi, kad standartiškai _more friends = better_, bet pasirodo, kai turi didelius kiekius draugų account'ų, tačiau negali atskirti kurie iš jų yra aktyvūs, o dauguma iš jų tokie ir nebuvo, tai tuščias srautas toli gražu nesukelia pasitenkinimo. Niekas nenori rėkti į tuštumą. Ironiška, bet jei užuot asimetrinės kontaktų sistemos tinklapyje būtų naudojama simetrinė, dėl ko G+ labiausiai ir skyrėsi nuo Facebook'o, tai ši problema būtų buvusi kiek lengvesnė - t.y. norint užmegzti kontaktą, kita pusė turi būti aktyvi ir priimti tavo pakvietimą. Taikant asimetriją reikėjo likti prie organinio augimo.
* Per didelis pasitikėjimas algoritmais, kurie turėjo už tave nuspręsti kas yra labiau verta dėmesio ir svarbu. Istoriškai tai Google'ui sekdavosi, tad buvo tikėtasi tai atkartoti ir čia. Kai svarbi ir nesvarbi komunikacija nėra atskiriama ir sumalama į vieną bendrą srautą ir paliekama algoritmams nuspręsti, ką vartotojai turi matyti. Kaip ir galima spėti - dalis postų tiesiog pasimeta ir būna tiesiog nepamatomi.
* Fundamentaliai Google+ nesprendė jokios naujos problemos. Facebook'as, Instagram'as, Youtube'as ar Twitter turi unikalias savo paskirtis. O pliusas nors ir sprendė kai kuriuos dalykus kitaip ir galbūt geriau, tačiau fundamentaliai, tai buvo dar vienas FB.
* > _After all people don’t go to social networking sites with the best features — they go to the ones that all their friends are on_

Galima pridėti ir dar kelias, ne tokias gyvybiškai svarbias, bet kalančias dar po vinį:

* Jokių read/write API nebuvimas. Nebuvo galima naudoti jokio kito kliento. Pvz. Twitter ar Reddit atvejai labai gerai parodo, kaip kiekvienas atskiras apps'as gali pateikti savo unikalų take'ą, kuris gali gan nemažai įtakoti pasitenkinimą serviso naudojimu. Tai taipogi reiškia, kad nebuvo galima automatizuoti postų rašymo ar importavimo iš kitų tinklų. Kitaip tariant, jei į daugumą soc. tinklų gali postinti parašęs postą tik kartą, Google+ reikalavo asmeniško prisilietimo.
* Tikrų vardų politika

Įdomu, kad socialinio tinklapio sukūrimui žmonių psichologija yra ne mažiau svarbi, nei technologija

## Why Netflix Should Sell Ads

> We earn consumer screen time, both mobile and television, away from a very broad set of competitors. We compete with (and lose to) Fortnite more than HBO. When YouTube went down globally for a few minutes in October, our viewing and signups spiked for that time.
>
> Our growth is based on how good our experience is, compared to all the other screen time experiences from which consumers choose. Our focus is not on Disney+, Amazon or others, but on how we can improve our experience for our members.

The trouble this Internet reality presents to Netflix: if content is abundant and attention is scarce, it’s easier to sell attention than content; Netflix’s business model, though, is the exact opposite.

Netflix, of course, sees this as a differentiator, and for a long time it was: linear TV had commercials, while Netflix had none. Linear TV made you wait for your favorite show, while Netflix gave you entire seasons at once. This was particularly compelling when Netflix had similar content to linear TV: why would you put up with commercials and TV schedules when you could just stream what you wanted to?

* [https://stratechery.com/2022/why-netflix-should-sell-ads/](https://stratechery.com/2022/why-netflix-should-sell-ads/)

## Web 3.0

Pastaruoju metu kyla vis daugiau diskusijų apie WEB 3.0. Tai gan abstraktus terminas, tačiau kiek suabsoliutinus: web1 buvo kiek chaotiškas, sudėtingai naviguojamas, tačiau užtat decentralizuotas. Kiekvienas norėdamas skelbti informaciją internete, turėjo būti pasikaustęs nemažu knowhow, ko pasekoje masiniam naudojimui jis buvo techniškai per sudėtingas ir riboto prienamumo.\
web2 viskas susicentralizavo į platformas ir taip užgimė keletas interneto gigantų, kurie turi pilną šių tinklų kontrolę, tačiau tokiu būdu šiomis platformomis galėjo naudotis milijardai žmonių.\
web3 pagal idėją vyktų natūrali evoliucija, kai viskas vėl decentralizuojama, išlaikant teigiamuosius web2 aspektus, kaip sistemų lengvumą naudotis ir randamumą.

Tačiau atidžiau pasinagrinėjus dabartinę web3 rinką, galima pastebėti, kad teiginiai apie decentralizavimą gali būti ne tokie jau ir teisingi: ganėtinai daug statoma aplink kelis dominuojančius API tiekėjus, o natūraliai atsirandantis naujų, praplėstų galimybių poreikis, kurių palaikymo naudojamose krypto technologijose dažnai nebūna - tik dar labiau skatina šiuos API tiekėjus plėstis, pildyti šiuos poreikius savo sprendimais ir taip vis labiau konsoliduojant viską į savo platformas. Tai išesmės vėl gaunasi tas pats web2, tik kitaip.

> _Given the history of why web1 became web2, what seems strange to me about web3 is that technologies like ethereum have been built with many of the same implicit trappings as web1. To make these technologies usable, the space is consolidating around… platforms. Again. People who will run servers for you, and iterate on the new functionality that emerges. Infura, OpenSea, Coinbase, Etherscan._

* [https://moxie.org/2022/01/07/web3-first-impressions.html](https://moxie.org/2022/01/07/web3-first-impressions.html)

