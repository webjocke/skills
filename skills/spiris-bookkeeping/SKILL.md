---
name: spiris-bookkeeping
description: Granska och, efter uttryckligt godkännande, hantera användarens bokföringskö i Spiris, med Spiris MCP som förstahandsval och webbläsaren som reserv. Använd när användaren vill börja eller fortsätta bokföra, stämma av omatchade bankhändelser, hantera uppladdade kvitton eller slutföra ej bokförda utkast.
---

# Bokföring i Spiris

Hjälp användaren att arbeta igenom oavslutad bokföring i det aktiva
Spiris-företaget. En begäran som ”börja med bokföringen” ger tillstånd till
skrivskyddad undersökning och ett åtgärdsförslag. Med undantag för tillståndet
att ändra dokumenttyp nedan ger den inte tillstånd att ändra något i Spiris.

## Regler som alltid gäller

- Använd alltid Spiris MCP i första hand för att läsa och ändra uppgifter. Använd
  den delade webbläsaren och Spiris webbgränssnitt endast för det som saknar stöd
  i MCP eller som MCP tydligt inte kan slutföra. Använd ingen annan
  bokföringsintegration.
- Börja skrivskyddat, med undantag för ändring av dokumenttyp enligt punkten
  nedan. Skapa eller ändra aldrig ett utkast, länka eller matcha poster,
  registrera en betalning, omvandla eller bokför ett utkast, skicka något eller
  gör någon annan bokföringsändring innan användaren uttryckligen har godkänt
  den aktuella numrerade åtgärden.
- Användaren ger ett stående tillstånd att ändra dokumenttypen för ett olöst
  uppladdat dokument mellan `Leverantörsfaktura` och `Kvitto` utan föregående
  godkännande. Använd undantaget endast så länge dokumentet inte är
  färdigbehandlat, länkat eller bokfört och endast när innehållet tydligt stöder
  klassificeringen. Tillståndet omfattar inte att skapa en leverantörsfaktura
  eller verifikation, länka filen eller bokföra något. Notera varje automatisk
  omklassificering och redovisa den i granskningen. Lämna dokumenttypen orörd och
  fråga användaren om klassificeringen är oklar. Försök först med Spiris MCP och
  använd annars Spiris webbgränssnitt under detta stående tillstånd. Om varken
  MCP eller webbläsaren är tillgänglig ska dokumentet lämnas orört och
  begränsningen rapporteras.
- Tolka aldrig tystnad, utebliven invändning eller ett tvetydigt svar som ett
  godkännande. Ett godkännande omfattar bara de väsentliga uppgifter som har
  presenterats.
- Hitta aldrig på ett kvitto, en faktura, motpart, ett affärssyfte,
  momshantering, konto, projekt, kostnadsställe eller någon annan uppgift som
  saknas. Användaren måste lämna nödvändiga underlag och sakuppgifter.
- Respektera låsta bokföringsperioder. Försök inte kringgå en låsning och flytta
  inte tyst en affärshändelse till ett annat datum.
- Föreslå bara åtgärder som faktiskt kan utföras genom Spiris MCP eller det
  inloggade Spiris-webbgränssnittet. Om en nödvändig åtgärd saknar stöd i båda
  ska det sägas tydligt; påstå eller antyd aldrig att den har utförts.

## MCP först och webbläsaren som reserv

Pröva inför varje delmoment först om Spiris MCP kan läsa uppgiften eller utföra
åtgärden. Använd MCP när det är möjligt. Gå inte över till webbläsaren enbart för
att gränssnittet verkar enklare eller mer bekant.

Öppna tidigt i varje bokföringskörning den delade webbläsaren på Spiris. Om
användaren inte redan är inloggad ska användaren omedelbart få en kort
arbetsuppdatering med en uppmaning att själv logga in i webbläsaren. Be aldrig om
lösenord, BankID-, tvåfaktors- eller återställningsuppgifter i chatten och fyll
inte i dem åt användaren.

Vänta inte passivt på inloggningen. Fortsätt samtidigt i bakgrunden med all
oberoende, skrivskyddad inventering och analys via MCP. Rör inte
inloggningsflödet medan användaren använder det. Kontrollera den delade
webbläsarsessionen igen först när en webbläsaråtgärd behövs. Om inloggningen ännu
inte är klar ska övrigt MCP-arbete fortsätta; rapportera till sist vilka punkter
som väntar på webbläsaren om inget annat arbete återstår.

Använd webbläsaren som reserv för både läsning och genomförande när motsvarande
MCP-funktion saknas, exempelvis för dokumentomklassificering, bokföringsmallar,
bankmatchning eller annan Spiris-funktion som endast finns i webbgränssnittet.
En tillfällig bilageadress som Spiris MCP lämnar får öppnas skrivskyddat i
webbläsaren för att granska det faktiska underlaget.

Skrivskyddad navigering i Spiris får ske innan planen godkänns. Alla ändringar i
webbläsaren följer samma godkännanderegler som MCP-ändringar, med
dokumentomklassificering som enda stående undantag. Ett godkännande av en exakt
beskriven åtgärd omfattar även att den genomförs i webbläsaren utan ytterligare
bekräftelse.

Kontrollera före varje webbläsarändring att rätt företag är valt och att de
synliga beloppen, datumen, kontona och dokumentreferenserna överensstämmer med
det godkända förslaget. Om gränssnittet visar oväntade värden, nya val eller en
annan följd än den godkända ska punkten stoppas enligt felhanteringen nedan.

Utför aldrig samma ändring genom båda kanalerna. Om ett skrivande MCP-anrop ger
ett osäkert resultat ska den aktuella statusen först kontrolleras skrivskyddat;
upprepa inte åtgärden i webbläsaren förrän det är säkert att MCP-anropet inte
genomfördes.

## Bygg hela granskningskön

Använd den period eller annan avgränsning som användaren anger. Undersök annars
hela den relevanta öppna bokföringsperioden fram till och med idag och ange
datumintervallet i granskningen. Läs först företagsinställningarna när land,
valuta, momsinställningar, bokföringslås, projekt eller kostnadsställen kan
påverka analysen.

Identifiera det aktiva företaget med namn och organisationsnummer i
granskningens inledning. Om identiteten inte kan fastställas eller verkar strida
mot användarens begäran ska arbetet stoppas innan bokföringsåtgärder föreslås
eller genomförs.

Samla in allt relevant oavslutat arbete innan några rekommendationer lämnas:

- omatchade bankhändelser på samtliga aktiva bankkonton;
- uppladdade kvitton och andra bilagor som saknar bokfört dokument, är olänkade
  eller endast är länkade till ett ej bokfört utkast;
- ej bokförda leverantörsfakturautkast och verifikationsutkast;
- kundfakturautkast när de ingår i bokföringskön;
- obetalda leverantörsfakturor som har förfallit eller snart förfaller samt
  förfallna kundfakturor som kan behöva följas upp; och
- andra tydligt oavslutade Spiris-poster som är relevanta för den valda perioden.

Ange alltid ett uttryckligt datumintervall när bankhändelser hämtas; annars
begränsar Spiris MCP normalt resultatet till den aktuella kalendermånaden. Följ
pagineringen tills samtliga sidor har granskats. Beskriv aldrig en ofullständig
första sida som hela kön.

Kontrollera även om svaret för bankhändelser anger att något konto eller resultat
har trunkerats, exempelvis genom `accountsTruncated`. Dela då upp datumintervallet
i mindre delar och hämta dem var för sig tills ingen del är trunkerad. Slå ihop
resultaten och ta bort dubbletter innan kön eller historiken analyseras.

Använd sju kalenderdagar som standard för `förfaller snart`, om användaren inte
anger en annan tidsgräns. Redovisa tidsgränsen och skilj tydligt mellan en
leverantörsfaktura som användaren kan behöva betala och en kundfaktura som kan
behöva drivas in. En förfallovarning är inte ett tillstånd att initiera en
betalning. Om en godkänd bokföringsåtgärd även kan skicka eller schemalägga en
bankbetalning ska den följden anges uttryckligen i förslaget; lämna annars själva
betalningen till användaren.

Korshänvisa köerna mot befintliga kundfakturor, leverantörsfakturor,
verifikationer, utkast, bilagor och matchade bankhändelser. Slå ihop poster som
avser samma affärshändelse till en granskningspunkt i stället för att visa
dubbletter. Bortsett från de efterfrågade förfallovarningarna är en obetald
faktura inte automatiskt oavslutad bokföring. Ta med den som en åtgärdspunkt när
det finns en tillhörande händelse att stämma av eller när användaren uttryckligen
ber om arbete med kund- eller leverantörsreskontran.

## Ta fram den föreslagna hanteringen

Analysera hela kön innan den presenteras. Använd följande prioritetsordning för
underlagen till varje enskild affärshändelse:

1. Kontrollera om det redan finns en kundfaktura, leverantörsfaktura,
   verifikation, ett utkast eller annat dokument som händelsen ska länkas eller
   matchas mot. Sök efter dubbletter innan en ny post föreslås.
2. Hitta den senaste verkligt jämförbara bokförda händelsen: samma motpart eller
   inköpsställe, händelsetyp, beskrivning och liknande omständigheter. Granska de
   faktiska konteringsraderna och dokumenthanteringen, inte bara rubriken.
3. Granska äldre jämförbara händelser när sådana finns för att avgöra om
   hanteringen är ett stabilt mönster eller ett undantag. Ge större vikt åt nära
   och aktuella exempel, men kopiera inte en tidigare kontering som verkar vara
   felaktig eller inte längre tillämplig.
4. Kontrollera den föreslagna hanteringen mot normal bokföringspraxis för
   affärshändelsen samt företagets land, kontoplan, momsinställningar, valuta och
   öppna bokföringsperiod.

Granska de uppgifter som väsentligen påverkar åtgärden: belopp och valuta,
datum, motpart, faktura- eller OCR-referens, debet- och kreditkonton, momssats
och momsbelopp, brutto-/nettoberäkning, projekt, kostnadsställe,
transaktionstext, bilagor, betalningshantering samt om leverantörsfaktura eller
verifikation är rätt dokumenttyp. Se historisk hantering som ett underlag, inte
som ett bevis.

Gissa inte om underlaget saknas, affärssyftet är oklart, jämförbar historik
motsäger sig själv eller hanteringen på annat sätt saknar tillräckligt stöd.
Rekommendera att avvakta och ställ en precis fråga eller begär exakt det
dokument som behövs. Fortsätt samtidigt att analysera övriga punkter så att
användaren får en samlad granskning.

## Återanvänd och föreslå bokföringsmallar

Kontrollera om det finns en relevant bokföringsmall i Spiris innan en punkt
utreds från grunden. Sök först via MCP och använd annars det inloggade
webbgränssnittet. Se en lämplig mall som en stark ledtråd, särskilt när den
överensstämmer med nyligen bokförda jämförbara händelser. Kontrollera ändå att
mallens konton, moms, dokumenttyp, dimensioner och betalningshantering passar den
aktuella händelsen. En mall är inte en auktoritativ källa och får inte väga
tyngre än motstridiga underlag.

Kontrollera om en användbar mall redan finns när en hantering är återkommande
och stabil, exempelvis en likadan månadsavgift. Om ingen finns och en mall kan
skapas genom MCP eller Spiris webbgränssnitt ska en mall föreslås i den
numrerade planen. Visa dess avsedda namn och användning, dokumenttyp, konto- och
momshantering, dimensioner samt vilka värden som ska vara rörliga. Skapa den
först efter att användaren har godkänt förslaget, med MCP som förstahandsval och
webbläsaren som reserv. Skapa inte mallar för engångshändelser eller mönster som
fortfarande kräver bedömning från fall till fall.

Påstå inte att en inbyggd Spiris-mall kan skapas om varken MCP eller
webbgränssnittet stöder det. Ta i stället med en kort, återanvändbar
konteringsanvisning i resultatet så att användaren kan konfigurera den eller
upprepa hanteringen manuellt.
Förklara hur användaren känner igen när mallen eller anvisningen är tillämplig,
vilka fält som fortfarande måste kontrolleras varje gång samt vilka tidigare
verifikationer och vilket datum anvisningen senast verifierades mot.

## Visa en samlad numrerad granskning

Begär inte beslut punkt för punkt under undersökningen. Presentera först en
samlad lista med beständig numrering när samtliga punkter har analyserats. Använd
ett nummer per affärshändelse och behåll samma nummer i efterföljande svar.

Visa följande för varje punkt:

- datum, motpart eller beskrivning, belopp och valuta, typ av post samt en
  användbar Spiris-referens;
- den exakta föreslagna åtgärden, inklusive vad som ska länkas, matchas, läggas
  i utkast eller bokföras;
- om åtgärden ska utföras via MCP eller, därför att MCP-stöd saknas, via
  webbläsaren;
- föreslagna konteringsrader och momshantering när en ny eller ändrad bokföring
  ingår;
- det bästa historiska exemplet, inklusive datum och referens, samt relevant
  motivering utifrån normal bokföringspraxis;
- eventuell befintlig lämplig mall eller förslag på en ny återkommande mall;
- förfallostatus och exakt förfallodatum när tiden är viktig;
- säkerhetsnivå med en kort motivering; och
- `Behöver från dig` när ett dokument, en förklaring eller ett val krävs.

När en ansvarsfull åtgärd ännu inte kan föreslås, skriv `Föreslagen åtgärd:
Vänta – bokför inte` och be om underlaget som saknas. Dölj inte osäkerhet bakom
ett konto eller en momssats som bara verkar rimlig.

Avsluta med att be användaren svara med numren, till exempel:

```text
1. Ja, gör det.
2. Vänta; jag skickar kvittot.
3. Godkänd.
4. Använd konto 6540 i stället.
```

Ange tydligt om ett godkänt förslag endast skapar ett granskningsbart utkast
eller både skapar utkastet och bokför det direkt. Ett godkännande av det senare
omfattar båda stegen utan ytterligare bekräftelse, men endast med exakt de
väsentliga uppgifter som visades. Ett tydligt `godkänn allt` kan godkänna alla
föreslagna åtgärder. Ett onumrerat svar som `ser bra ut` är bara ett godkännande
om omfattningen är otvetydig; fråga annars.

Lägg efter den numrerade granskningen till en kort checklista med rubriken `Det
här behöver du göra`. Samla allt användaren själv behöver hantera, exempelvis
att lämna saknade kvitton eller förklaringar, betala leverantörsfakturor som
snart förfaller eller har förfallit och följa upp förfallna kundfakturor. Hänvisa
till de beständiga punktnumren så att checklistan inte blir en andra kö.

## Utför endast godkända åtgärder

Koppla användarens svar till de beständiga punktnumren. Gör inget med punkter som
har avslagits, skjutits upp, besvarats otydligt eller inte nämnts.

Läs in och verifiera företagsidentiteten som visades i granskningen på nytt
innan den första godkända ändringen. Gör kontrollen även i webbgränssnittet före
den första webbläsarändringen. Om identiteten inte stämmer ska hela körningen
stoppas.

Läs omedelbart före varje godkänd ändring in de berörda Spiris-posterna på nytt
och kontrollera att dokumentidentitet, status, belopp, valuta, datum och övriga
väsentliga uppgifter fortfarande stämmer med förslaget. Om något väsentligt har
ändrats ska just den punkten stoppas och avvikelsen sparas till resultatmeddelandet.
Fortsätt med övriga oberoende, godkända punkter. Den ändrade punkten kräver ett
reviderat förslag och ett nytt godkännande senare.

Använd i första hand Spiris arbetsflöde med ett ej bokfört utkast när en ny
huvudbokspost ska skapas och ett sådant arbetsflöde finns. Fyll utkastet med de
godkända uppgifterna, läs in det skapade utkastet på nytt och jämför det med
förslaget före bokföring. När det godkända förslaget angav `skapa och bokför`
ska ett överensstämmande utkast bokföras direkt utan ytterligare bekräftelse.
Använd den kontroll mot förväntat totalbelopp som konverteringsverktyget erbjuder.
Om utkastet avviker väsentligt ska punkten stoppas utan bokföring och det
kvarvarande utkastet rapporteras. Om förslaget endast lovade ett utkast ska
arbetet stanna när utkastet har skapats.

Utför en ändring utan utkastflöde endast när exakt den åtgärden och dess
väsentliga uppgifter visades och godkändes. Bilagelänkning,
betalningsregistrering och bankavstämning är separata ändringar och måste ingå i
det godkända förslaget.

Om en skrivande åtgärd returnerar ett fel eller ett osäkert resultat ska den
aktuella statusen undersökas innan ett nytt försök övervägs. Upprepa aldrig en
bokförings- eller betalningsåtgärd blint. Om något steg för en punkt misslyckas
eller ger ett oväntat resultat ska återstående steg för just den punkten stoppas,
eventuella delresultat bevaras och rapporteras och arbetet fortsätta med övriga
oberoende, godkända punkter. Stoppa hela körningen endast när problemet är
systemomfattande eller gör återstående åtgärder osäkra, exempelvis fel företag,
autentiseringsfel, bokföringslås eller ett omfattande avbrott i Spiris MCP.

Rapportera resultatet under de ursprungliga punktnumren, inklusive skapade eller
länkade Spiris-referenser, automatiska omklassificeringar, delresultat, fel och
kvarstående frågor samt om respektive åtgärd utfördes via MCP eller
webbläsaren. Lämna den samlade resultatrapporten efter att alla säkra, godkända
punkter har försökts i stället för att avbryta hela körningen för en misslyckad
punkt. Hämta därefter de skrivskyddade köerna på nytt och sammanfatta vad som
återstår.
