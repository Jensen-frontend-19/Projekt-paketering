# Individuellt projekt: TDD och Docker
## Byggverktyg

1. [Introduktion](#1-introduktion)
1. [Uppdragsbeskrivning](#2-uppdragsbeskrivning)
1. [Level ups](#3-level-ups)
1. [Inlämning](#4-inlämning)
1. [Bedömning](#5-bedömning)
1. [Appendix: förslag till projektplan](#6-appendix-förslag-till-projektplan)


---
### 1. Introduktion
> *Meetup is about connecting people with something in common. While the connections begin online, the real memories are made at events. Meetup events are real-life gatherings where members and organizers get together to connect, discuss, and practice activities related to their shared interests.*

Du ska bygga en Vue-app för meetups och publicera den i en Docker-container med valfri molntjänst. Användare ska kunna:
+ se kommande meetups,
+ anmäla sig till meetups,
+ recensera en meetup man har varit på.

Se https://www.meetup.com/ för inspiration.


---
### 2. Uppdragsbeskrivning
*Fråga läraren om du vill använda andra tekniker än de som står här.*
#### Vue-app
Du ska bygga en Vue-app med Vue CLI. Använd en egen fil för appens data. (Exempel i repot 05-docker. Det är ok att använda localStorage.) Appen ska vara användarvänlig och användbar.


#### TDD
Du ska använda TDD när du utvecklar Vue-appen: red, green, refactor. Skriv enhetstester för varje komponent. Om du använder AJAX eller databasanrop så ska de mockas. (Test av router kallar vi integrationstest - att komponenter fungerar tillsammans.)

*Tips! Testa inte allt, utan välj ut det som är viktigast att testa. En tumregel är att testa sådant som man bryr sig om. Exempel: bryr jag mig om vilken text det är på en specifik rubrik?*


#### Docker image
Bygg en image som innehåller appen. Observera att du behöver inkludera en webbserver i `Dockerfile` för att appen ska kunna köras.


#### Deploy online
Publicera appen i en Docker container med valfri molntjänst, till exempel Heroku.

[Publicering, miniguide](deploy.md)

*Tips! Vänta inte med deploy till sista dagen. Skriv upp de kommandon du använder för att bygga en image. (Du kommer behöva göra det flera gånger.) Gör en MVP (minimum viable product) och publicera den. Sedan jobbar du vidare tills du är klar med appen.*

---
### 3. Level ups
Implementera level ups för att få högre betyg och lära dig mer.

**Continuous Delivery** - prova tekniker för CD, till exempel GitHub Actions, GitLab eller Jenkins. Skriv i inlämningen vad du har använt.

**Planera event** - användare kan lägga till egna events.

**API/databas** - appen använder en databas eller ett API för att spara events. Tips på API: https://jsonbin.org/, https://jsonbin.io/

**Systemtester** - testa hur komponenter fungerar tillsammans

**Acceptanstester** - testa att de övergripande kraven är uppfyllda. Exempelvis kan man testa inloggning genom ett längre test: skriv in text i textfälten för användare och lösenord, klicka på knappen, kontrollera att appen visar att man är inloggad.

**Sortera/filtrera** - använda ett sökfält för att begränsa vilka events som visas.


---
### 4. Inlämning
Skapa en textfil med namn `inlämning-Anna-Andersson-FRK19S.txt`, där du byter ut namnet och klassen mot ditt eget. Lämna in filen på LearnPoint. Textfilen ska innehålla:

1. Länk till ditt GitHub-repo (kontrollera att repot är publikt)
2. Berätta vilken molntjänst du använt för att publicera
3. Länk till den publicerade appen
4. Berätta vilka level ups du har implementerat
5. Demonstrera att du kan resonera och reflektera kring kursinnehållet, genom att berätta vad du tycker är det viktigaste kursen har handlat om.


---
### 5. Bedömning
**För godkänt** på projektet ska du
+ lösa uppgiften enligt beskrivningen ovan

**För väl godkänt** på projektet ska du
+ implementera level ups
+ demonstrera att du behärskar kursens innehåll, genom att resonera och reflektera kring kursinnehållet

---
### 6. Appendix: förslag till projektplan
Ett förslag på hur du kan strukturera ditt projekt:
1. börja med en skiss i Figma
2. skapa en tom Vue-app med README.md och en Dockerfile
3. välj en molntjänst och publicera den; skriv upp stegen du gick igenom i Readme (så blir det lätt att göra om dem)
4. börja implementera Vue-appen med hjälp av TDD
5. när du börjar bli färdig: skriv klart readme-filen
6. merge till master, push till gitHub, publicera Docker container i molnet och lämna in

*Lycka till!*

[Toppen av sidan](#1-introduktion)
