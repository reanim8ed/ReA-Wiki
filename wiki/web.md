# Web

### Anonymous Email Forwarding

Kai Firefox pristatė savo Relay servisą, kuris forwardina el. laiškus panašiu principu, kaip tai daro Apple su "Sign In With Apple" opcija, kuri leidžia vartotojui paslėpti savo tikrąjį el.pašto adreso nuo paslaugos tiekėjo, tokio pobūdžio servisas mane visai  sudomino. Tai suteikia galimybę kiekvienoje svetainėje naudoti unikalų el. pašto adresą ir kai pradedamas gauti spam'as, galima tiksliai identifikuoti iš kur buvo nuleakinti duomenys ir atjungti siuntimą vos vieno mygtuko paspaudimu. O taipogi tai dar viena papildoma saugumo priemonė, nes nutekėjus prisijungimo duomenims, niekur kitur jų pernaudoti nepavyktų, net jei slaptažodis ir būtų naudojamas tas pats.

Tačiau šis servisas turi 2 ryškius minusus. Pirmiausia, tai nemokamoje versijoje galima susikurti vos tik 5 alias, tad iš esmės juos reikėtų pernaudoti, o tai iš esmės panaikina tokio serviso vieną iš esminių privalumų. Tai būtų galima išspręsti su premium versija, kuri kainuoja vos 1€/mėn. Tačiau čia ir antrasis minusas - tai Mozilla servisas, kurių comitmentu ir projekto ilgaamžiškumu galima sudvejoti. Yra gan didelė tikimybė, jog po poros metų, jie shiftins savo fokusą ir sugalvos servisą uždaryti (geras to pvz buvo jų Send servisas, gyvavęs vos metus).

Tad teko pasidomėti alternatyvomis:

* [https://anonaddy.com](https://anonaddy.com) - nemokami alias, tačiau ribotas bandwidth
* [https://simplelogin.io](https://simplelogin.io) - neribotas srautas, tačiau nemokamas tier'as turi tik 15 alias apribojimą

Anonaddy - geresnis pasirinkimas, jei norima naudoti nemokamai, o jei ir mokama - jis yra pigesnis. Tačiau SimpleLogin labiau išdirbtas bei nukreipus savo domain'ą, turi catch-all funkcionalumą, kai pašto dėžutės alias susikuria automatiškai, kai tik į tą domeną pirmą kartą atsiunčiamas laiškas, kas yra labai neat funkcija, nes netrukdo registracijos flow ir galima random alias susigalvoti tiesiog bepildant registracijos formą.
