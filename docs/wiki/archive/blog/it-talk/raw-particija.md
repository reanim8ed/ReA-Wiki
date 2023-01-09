---
description: 'Publikuota: 2014-02-06'
---

# RAW particija

![](../../../.gitbook/assets/hard_disk_head_crash.jpg)

Pradžioje turėjau nešiojamąjį kompiuterį, kurį tempdavausi į darbą, tačiau vėliau nusprendus susirinkti našų stacionarų kompiuterį, jį pardaviau, o duomenų, bei naudojamų aplikacijų pernešimui pasirinkau išorinį kietąjį diską. Atėjus į darbą, pasijungi diską, pasileidi savo programas ir svetimame kompiuteryje jautiesi beveik, kaip savoje aplinkoje. Tačiau problema, su kuria kartas nuo karto susiduria išorinių kietųjų diskų savininkai – „nušokusios“ particijos. Ką tai reiškia?

Kai programai yra nurodoma įrašyti \(arba perskaityti\) failą į išorinį įrenginį, šis procesas neįvyksta akimirksniu, failas padalinamas į dalis ir jo paketai įrašinėjami į laikmeną vienas po kito ir jei tuo metu, kai vyksta šio failo perkėlimas, diskas netikėtai atjungiamas, tai geriausiu atveju jūs tiesiog turėsite sugądintą, neužbaigtą failą diske, kurį ištrinsite ir kelsite failą nuo pradžių. Tačiau kartais gali nutikti kur kas blogiau – diskas gali būti atjungiamas būtent tuo metu, kai buvo atnaujinama failų sistemos lentelė, kurioje iš esmės yra pateikiami jūsų saugomų failų adresai, kad kompiuteris žinotų į kurią vietą diske reikia kreiptis norint pasiekti vieną ar kitą failą. Tokiu atveju įvyksta klaida, susigadina failų lentelės vientisumas, arba kitaip tariant, atsiranda „blogų“ sektorių ir kitą kartą pajungus šį kietąjį diską, windows’ai gali jo tiesiog nebeatidaryti ir vietoj įprastos NTFS failų sistemos rodyti užrašą RAW, o bandant atidaryti tokį diską, tiesiog prašoma jį suformatuoti, taip prarandant visus viduje esančius failus. Siaubas gali ištikti ne tik, jei ten buvo išties svarbūs dokumentai, bet ir tarkime porą šimtų GB jūsų kruopščiai rinktos muzikos, kaip kad buvo mano atveju. Bet koks duomenų pasiekimas tiesiog nebegalimas :/

Ši bėda man buvo nutikusi jau ne vieną kartą ir pamenu patį pirmą kartą griebiausi duomenų atsatymo \(recovery\) programų, kaip kad TESTDISK. Šios programos sugebėjo ištraukti mano duomenis, bet kadangi, tai buvo beveik pilnas 1TB talpos diskas, procesas ne tik, kad truko kelias dienas, tačiau tam reikėjo net kelių kompiuterių, nes atkuriant duomenis, reikia vietos, kur padėti atkurtus failus. Sprendžiant iš to, kad dėl tos pačios bėdos į mane jau buvo kreipęsi ne vieną kartą, tai sprendžiu, kad bėda ne tokia jau reta ir būtent dėlto ir noriu pasidalinti paprastu šios bėdos sprendimo būdu.

**Kaip sutvarkyti RAW particiją?**

Pirmiausia, tai kai bandant atidaryti diską, jūsų prašoma šį diską suformatuoti, tai būtinai to NEDARYKITE, nes tokiu atveju duomenų atsatymas šiuo būdu tikrai nepagelbės ir gali būti išvis ganėtinai problematiškas ir ko gero atliktas tik tuom užsiimančių profesionalų.

Jei disko dar nespėjote suformatuoti, atliekam šiuos žingsnius:

-Spaudžiame Start ir paieškos laukelyje įvedame „cmd“ \(be kabučių\);

-Spaudžiame ant pirmo rezultato dešiniu klavišu ir pasirenkame „Run as administrator“;

-Atsidarys komandinės eilutės langas, kuriame įrašome komandą „chkdsk F: /f“, kur F: yra jūsų sugadinto išorinio kietojo disko raidė;

-Baigus disko skanavimą ir pranešus apie sėkmingą darbo užbaigimą, nueikite į MyComputer ir pabandykite vėl atidaryti diską. Turėtų pavykti.

/f yra skirtas klaidų taisymui. Pirmiausia paleiskite jį, nes jis trunka gerokai trumpiau ir gali iškarto padėti. Jei tai nepadėtų, tada pabandykite /r variantą, kuris nustato blogus sektorius ir pasistengia atkurti informaciją juose, tačiau užtrunka tikrai gerokai ilgiau, ypač jei diskas yra didelės talpos. Mano atvejais užtekdavo tiesiog /f

Jei jums pasiseks – visi duomenys bus savo vietose ir jokių failų atkūrimų, ilgų kančių ar formatavimo ir duomenų praradimo. Kartais atrodytų didelės bėdos, sprendžiamos visai paprastai ;\)

