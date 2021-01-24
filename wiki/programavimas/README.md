# Programavimas

## Notes

* A good engineer never assumes the perfect reliability of the components of the system. He or she builds in redundancy to protect the integrity of the total system.
* Software engineering is what happens to programming when you add time and other programmers.
* Engineering is figuring out how to do what you want with what you’ve actually got
* You can’t guilt yourself into doing things you want to accomplish. You’ll always resist and make excuses. The only way is to enjoy the act of doing them.
* C programmer’s motto: “Build upon the work of others”
* [10x programeriai](http://10x.engineer/) vs [1x programerius](https://1x.engineer/)
* "Premature optimization is the root of all evil". This can result in a design that is not as clean as it could have been or code that is incorrect, because the code is complicated by the optimization and the programmer is distracted by optimizing. This applies more broadly than just for code. Abstraction is a form of optimization and shouldn't be done before the space has been properly explored to know what abstractions should be built.
* Integrity compounds infinitely, and capability always decays.
* Would I ever leave this company? Look, I'm all about loyalty. In fact, I feel like part of what I'm being paid for here is my loyalty. But if there were somewhere else that valued loyalty more highly, I'm going wherever they value loyalty the most.
* Typically, the more expensive the product the longer the sales page needs to be.

## Pomodoro for Software Development

Yra nemažai tyrimų, kurie rodo pertraukėlių naudą dirbant intensyvų protinį darbą. Nors kartais galbūt ir nesijaučiame, jog tos pertaukėlės taip jau reikėtų, tačiau jos padeda smegenims recoverinti, taipogi tokių dažnų pertraukėlių metu labai rekomenduoti atsistoti iš savo vietos, bent kiek pajudėti. Tad tai ne tik sveikiau dėl bendros fizinės sveikatos, tačiau ir bendras produktyvumo lygis ilgesniu laikotarpiu visgi gaunasi aukštesnis. 

Tad atrodytų, jog Pomodoro technika turėtų išties puikiai tikti programavimo srityje, nes kaip bebūtų tai sėdimas ir labai intensyvaus smegenų darbo reikalaujantis užsiėmimas. Tačiau standartinis 25-5 Pomodoro variantas visgi veikia gan prastai, darbo etapai tampa per trumpo, o dėl vadinamojo "Task Recovery Lag" grįžti į darbinį, minčių flow prireikia laiko ir kartais tai gali trukti net iki 15 minučių. Tačiau Pomodoro galima taikyti ir kitokiais intervalais. Populiariausi - 45:15, 52:17, 90:15.  
Iš asmeninės patirties, manau, kad geriausiai man asmeniškai "sueina" 50:10 - pertraukos nėra pernelyg ilgos, kai tiesiog nebėra kuom užsiimti per tokias ilgas pertraukas. Darbo etapas pakankamai ilgas, kad per jį spėtum išties atlikti nemažą porciją darbo ir po tiek laiko trumpa pertraukėlė tampa ganėtinai natūrali. Na ir galiausiai - sekti tokius ciklus tampa itin paprasta, užtenka vos tik užmesti akį į laikrodį ir iškarto tampa aišku, kiek laiko liko iki pertraukos pradžios ar pabaigos.

[https://www.softwaremeadows.com/posts/the\_50-10\_time\_box\_revising\_pomodoro\_for\_software\_development/](https://www.softwaremeadows.com/posts/the_50-10_time_box_revising_pomodoro_for_software_development/)

## Cookie-to-Header CSRF Token

The Cross-Site Request Forgery \(CSRF\) attack is when an _attacker_ website is able to successfully submit a request to _your_ website using a logged-in user's cookies. This attack is possible because browsers will "helpfully" include cookies with any request to your site, regardless of where that request originated from.

[https://dev.to/nas5w/using-a-cookie-to-header-csrf-token-in-single-page-applications-ngh](https://dev.to/nas5w/using-a-cookie-to-header-csrf-token-in-single-page-applications-ngh)

## The Iceberg Secret, Revealed

Have you ever noticed that on these custom projects, the single most common cause of overruns, failures, and general miserableness always boils down to, basically, “the \(insert expletive here\) customer didn’t know what they wanted?”

Customers Don’t Know What They Want. Stop Expecting Customers to Know What They Want. It’s just never going to happen. Get over it.

Instead, assume that you’re going to have to build something anyway, and the customer is going to have to like it, but they’re going to be a little bit surprised. YOU have to do the research. YOU have to figure out a design that solves the problem that the customer has in a pleasing way.

You know how an iceberg is 90% underwater? Well, most software is like that too. That’s not the secret. The secret is that People Who Aren’t Programmers Do Not Understand This.

* If you show a nonprogrammer a screen which has a user interface that is 90% worse, they will think that the program is 90% worse.
* If you show a nonprogrammer a screen which has a user interface which is 100% beautiful, they will think the program is almost done.

[https://www.joelonsoftware.com/2002/02/13/the-iceberg-secret-revealed/](https://www.joelonsoftware.com/2002/02/13/the-iceberg-secret-revealed/)

## The steady stream of new issue trackers

I think the reason we see a steady stream of new issue trackers is that teams are trying to fix with software what are people problems.

New issue trackers feel faster for the same reason switching browsers tends to feel faster—you're getting rid of all of the crap you piled up in the old one. Don't migrate your backlog, start with only a couple engineers in a new issue tracker, and suddenly, wow!, this new tool is so much better!

But I don't think it really solves the problem. For most organizations, tracking tickets is a solved \(by many products\) problem. Starting with a new tool has the appearance of making things better, but leads to the same place. The problem is not the tool, it's the structure of the organization.

[https://news.ycombinator.com/item?id=23693029](https://news.ycombinator.com/item?id=23693029)

## Why Learning to Code is So Damn Hard

When you first start learning, the set of things you need to understand is narrow. Everyone, regardless of goals or language or background, needs to figure out what a `for` loop is, how to build conditional logic, and other basic structures of programming syntax. There ultimately aren't even that many of these fundamental concepts so the Scope of Knowledge during that phase is very narrow.

As soon as you get away from the basics, you see a rapid broadening of the Scope of Knowledge as you need to begin picking up things that are more difficult like understanding errors and _when_ to use the code you know know _how_ to use. This is different because there is no "correct" answer to a clear question... things get fuzzy.

When you progress into the third phase, the scope of knowledge balloons wider. You now need to understand what tools to use, what languages to learn, underlying CS fundamentals, how to write modular code, object-orientation, good style, and how to ask for help \(to name just a few\). Every trip to Google or Hacker News takes you down another set of rabbit holes and overwhelms you with more things you don't know but feel like you should.

_You don't know what you don't know._

[https://www.thinkful.com/blog/why-learning-to-code-is-so-damn-hard/](https://www.thinkful.com/blog/why-learning-to-code-is-so-damn-hard/)

## Single worst strategic mistake that any software company can make: decide to rewrite the code from scratch

Programmers are, in their hearts, architects, and the first thing they want to do when they get to a site is to bulldoze the place flat and build something grand. We’re not excited by incremental renovation: tinkering, improving, planting flower beds.

There’s a subtle reason that programmers always want to throw away the code and start over. The reason is that they think the old code is a mess. And here is the interesting observation: they are probably wrong. The reason that they think the old code is a mess is because of a cardinal, fundamental law of programming: It’s harder to read code than to write it.

It’s important to remember that when you start from scratch there is absolutely no reason to believe that you are going to do a better job than you did the first time. 

[https://www.joelonsoftware.com/2000/04/06/things-you-should-never-do-part-i/](https://www.joelonsoftware.com/2000/04/06/things-you-should-never-do-part-i/)

## Procrastination is driven by our desire to avoid difficult emotions

Words of warning from a not so young \(36\) chronic procrastinator with a rather messed up life: Take it seriously. I'm not talking about reading HN in your 7th work hour when doing stupid Excel sheets. I'm talking about messing up years and years of your life. I believe it's a symptom of some deeper issues and it won't go away from alone. Lack of sleep, stress, work overload, information overload amplify the effects but once it crept into your life outside of work it really can wreak havoc. Simple things start to become complicated and you are in a constant negative feedback loop. The worst is that you procrastinate not only work but rather your own existence because you'll constantly attempt to catch up but just can't.

[https://news.ycombinator.com/item?id=23537317](https://news.ycombinator.com/item?id=23537317)

## The greatest of all weaknesses is the fear of appearing weak. 

Tai viena iš priežasčių, kaip programavimo srityje dažnai apima _Impostor_ sindromas.   
Vienas iš svarbiausių React kūrėjų [straipsnyje rašo](https://overreacted.io/things-i-dont-know-as-of-2018/):

> _First, there is often an unrealistic expectation that an experienced engineer knows every technology in their field. Have you seen a “learning roadmap” that consists of a hundred libraries and tools? It’s useful — but intimidating._

> _What’s more, no matter how experienced you get, you may still find yourself switching between feeling capable, inadequate \(“Impostor syndrome”\), and overconfident \(“Dunning–Kruger effect”\)._

> _We can admit our knowledge gaps, may or may not feel like impostors, and still have deeply valuable expertise that takes years of hard work to develop._

> _I’m aware of my knowledge gaps \(at least, some of them\). I can fill them in later if I become curious or if I need them for a project. This doesn’t devalue my knowledge and experience. There’s plenty of things that I can do well. For example, learning technologies when I need them._

## Law of Software Envelopment

> Every program attempts to expand until it can read mail. Those programs which cannot so expand are replaced by ones which can.”

Coined by Jamie Zawinski to express his belief that all truly useful programs experience pressure to evolve into toolkits and application platforms \(the mailer thing, he says, is just a side effect of that\).

