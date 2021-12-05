---
Title: Load
Description: Load
Template: analysis
---

# Load
I denna rapport behandlas analys av laddningstider för de tre största mobiloperatörerna i Sverige. Rapporten går först igenom urval och metod, varefter resultat
för de olika webbsidorna presenteras, följt av en analys.

###Urval
-----------------------
 
För denna uppgift har jag valt att undersöka hemsidor för de tre största mobiloperatörerna i Sverige: [Tele2](http://www.tele2.se),[Telia](http://www.telia.se) och [Telenor](http://https://www.telenor.se/). Detta urval gjordes då detta är en bransch där de olika företagen har snarlika affärsmodeller och liknande sidupplägg på sin hemsida, vilket underlättar jämförelser kring laddningstider. Därtill kan det finnas förväntningar kring att företag inom telekombranschen bör ha bra förståelse för olika webbteknologier, varför det vore intressant undersöka om detta stämmer överens med verkligheten.
 
###Metod
-----------------------
Data för analysen har inhämtats på två sätt, dels med hjälp av inspekteringsfunktionen i webbläsaren Firefox, där data rörande nätverksöverföringar har noterats för vardera sida och dels med hjälp av verktyget Google PageSpeed. 

För varje företag har mätningar gjorts på tre sidor: förstasidan, mobiltelefoner och mobilabonnemang. Den data som mäts i webbläsaren är som följer: laddningstid, totalt antal resurser sidans storlek samt överförd storlek. Webbläsarmätningarna genomfördes tre gånger för varje sida, varav snittet av de tre mätningarna noterades. Det bör noteras att Telenors sida i begränsad utsträckning använder sig av sk. “lazy loading”, dvs. laddning av resurser efterhand som de blir synliga, varför det inte var möjligt att få fullt jämförbara mätningar om man laddade in hela sidan. Därför valde jag att för testet mäta laddning av innehåll “above the fold”, dvs. utan scrollning.

Från Google PageSpeed hämtade jag information om “first contentful paint” (FCP), dvs. tiden det tar innan första rendering till sidan har skett samt “largest contentful paint” (LCP), dvs. tiden för rendering av det största synliga bild- eller textblocket på skärmen. För LCP och FCP använde jag Googles samlade data från de senaste 28 dagarna och ej resultat som genererats via min uppkoppling. Jag har även noterat de viktigaste förbättringar/åtgärder som föreslagits av verktyget.
 
###Resultat
-----------------------

Först bör det noteras att jag har utfört analyserna via mobil 4g anslutning, varför resultaten kan vara missvisande. Jag har enligt bästa förmåga genomfört mätningarna under liknande uppkopplingsförhållanden och har bortsett från kraftigt utstickande resultat, då dessa resultat med hög sannolikhet har varit en följd av ostabil uppkoppling.
 
Resultaten har sammanfattats i tabellen nedan:
<iframe class="load-table" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ2O7h8aLuHAZbEc2W70tDdTpnbfBj5_d6VJku6-7XKY4L_FdWuomxSZS9OHFzk4phsVm9nhA2is7Hm/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false"></iframe>
 
####Telia
![Telia](../image/telia.jpg){.screenshot}

Samtliga av Telias hemsidor gavs betyget icke godkänt av Google PageSpeed. Även min egen upplevelse var något lidande då större bilder tog relativt lång tid att ladda, samtidigt som innehåll som annars skulle hamna “under the fold” renderades synligt och sedan pressades ner. Dock upplevdes det som att sidan relativt snabbt blev responsiv, även om inte alla bilder laddats in.
Google PageSpeed föreslog en rad förbättringar på både mobil och dator som skulle kunna göras över de tre sidorna, varav följande föreslogs för samtliga sidor: att skicka bilder i modernare filformat; koda bilder mer effektivt; använda bilder av rätt storlek; reducera Javascript och CSS som inte används och ta bort resurser som blockerar rendering. Av dessa problem verkar det att optimering framförallt behöver göras när det gäller att använda bilder av rätt storlek, och att reducera CSS och Javascript. Det sistnämnda kan bekräftas då t.ex. sidan för mobilabonnemang använde javascript på sammanlagt 4,72MB och CSS på 1MB.
 
####Tele2
![Tele2](../image/tele2.jpg){.screenshot}

Av de tre webbplatserna fick Tele 2s webbplats bäst betyg av Google PageSpeed, med godkänt för samtliga sidor på dator samt för förstasidan på mobil. Resterande två sidor fick underkänt på mobil. Tele2s hemsida kändes överlag kvickare än de två andra sidorna, och resultatet från mina egna mätningar bekräftar detta, med kortast laddningstid av de tre. Det enda förslag som gavs för samtliga sidor för både mobil och dator var att reducera JavaScript som inte används. Förslag gavs även, för framförallt mobilsidorna, att skjuta upp inläsning av innehåll som inte visas på skärmen, att ta bort resurser som blockerar rendering och att använda bilder av rätt storlek. Bilder var överlag väloptimerade med mindre filstorlekar än både Telia och Telenor. T.ex. var den största bildfilen på förstasidan ungefär 4 gånger mindre än Telias. Tele2 är också det företag som har kraftigast komprimering vid överföring, med överförd storlek mindre än hälften av faktisk storlek för alla tre sidor. Javascript verkar vara den största möjligheten för optimering, vilket blir tydligt med 2,99MB av Javascriptfiler på två av sidorna.
 
####Telenor
![Telenor](../image/telenor.jpg){.screenshot}

Telenor skiljer sig från de två andra sidorna då de använder sig av sk. “Lazy loading”, dvs. att förfrågningar görs och innehåll laddas allt eftersom det visas upp, vilket gör att jämförelser blir något svårare. Det sagt så hade Telenor i mina egna mätningar sämst sammanlagda laddningstider av de tre, även om jag ej scrollade sidan och endast höll mig “above the fold”. Detta verkar bekräftas av Google PageSpeed som gav samtliga sidor förutom förstasidan på dator underkänt. När det kommer till de viktigaste föreslagna åtgärderna liknade dessa överlag de förslag som gavs för Telias hemsida, dvs. att använda modernare bildformat, använda bilder i rätt storlek, reducera Javascript som inte används och att ta bort resurser som blockerar rendering. Ensamt bland de tre företagen föreslogs även textkomprimering för mobiltelefonsidan. Detta problem kan möjligtvis bekräftas av den, jämfört med Tele2, sämre komprimeringen, med reduktion i storlek på cirka 30% jämfört med över 70% hos Tele2.
Dessa resultat bekräftas när man tittar på faktiska filstorlekar i webbläsaren, med bilder som i filstorlek ofta är ca. 4 större än Tele2 och som mest 3.43MB i Javascriptfiler.
 
###Analys
-----------------------
Efter analys av resultat både från egna mätningar i webbläsaren och mätningar gjorda av Google PageSpeed var det tydligt att de två största problemen som verkar påverka sidornas laddningstid är dåligt optimerade bilder, både vad gäller filformat och storlek och dåligt optimerad Javascript-kod. Samtliga tre sidor hade problem med stora mängder Javascript, varav en del inte verkar användas att döma av resultat från PageSpeed. Det sagt kan det vara svårt att avgöra i hur stor utsträckning detta kan minskas då mycket kod verkar användas för handelsfunktioner. Minifiering verkar inte heller vara ett problem då detta (som förväntat) utförs på samtliga sidor. 

Vad gäller bilder verkar det största problemet, i huvudsak hos Telenor och Telia, vara användning av bilder av fel storlek, i synnerhet för produktbilder, samt kanske för hög bildkvalitet. Vad gäller PageSpeeds förslag att använda modernare bildformat som WebP och AVIF blir detta något svårare att tillämpa då stödet för dessa filformat ännu inte är fullt implementerat, i synnerhet för AVIF, och stödet är dåligt bland äldre webbläsare.

Om man ska rangordna webbplatserna både baserat på mina egna mätvärden och betyg från Google PageSpeed placeras Tele2 utan tvekan högst upp. Även om de verkar ha vissa problem med överflödig laddning av Javascript så har de lyckats lösa komprimering, framförallt bildkomprimering, väl utan märkbart avkall på upplevd kvalitet. När det kommer till andra och tredjeplats är det svårare att avgöra. Enligt Google PageSpeeds betyg är Telia den webbsida som är sämst optimerad av de tre, följt av Telenor. Telia har enligt under tid insamlad data från PageSpeed sämst laddningstider, medan det är jämnare mellan Telenor och Tele2. I mina egna mätningar var Telenor den sida som hade längst sammanlagda laddtider, som dessutom blev desto längre om man räknar med resurser som laddas in efterhand. Telia var dock inte långt därefter. Båda sidor dras också med liknande problem vad gäller överflödig Javascript, mindre komprimerade bilder och felaktiga bildstorlekar. Därför, efter samlad bedömning placerar jag de två webbsidorna på delad andra plats. 

Vad gäller egna preferenser för laddningstid är jag relativt förlåtande då jag är van vid instabila internetuppkopplingar. Dock så anser jag att väsentligt och omedelbart synligt innehåll ska vara laddat och kunna interageras med inom cirka 4 sekunder för att sidan ska kunna uppfattas som snabb. Av de tre webbplatserna var det endast Tele2s hemsida som klarade av detta och deras hemsida kändes både kvickare och mer lättviktig än konkurrenternas hemsidor. Varken Telia eller Telenor klarade av denna gräns och kunde vid extrema tillfällen ta över 30 sekunder att ladda, något jag inte upplevde på Tele2s hemsida.
(Som nämnts ovan bortsåg jag från dessa resultat då de troligen påverkats av instabil uppkoppling.)

Denna analys och rapport har utförts enskilt av Juhani Kotaniemi.
