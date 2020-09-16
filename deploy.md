# Miniguide till publicering av Docker image
### Heroku

Det finns två sätt att publicera en image till Heroku: med *container registry* och med *yml-fil*. I båda fallen behöver du ha med en webbserver i image-filen, till exempel http-server eller nginx.

#### Container registry
Läs mer här:
+ [Dockerize Vue app](https://vuejs.org/v2/cookbook/dockerize-vuejs-app.html)
+ [Container registry and runtime](https://devcenter.heroku.com/articles/container-registry-and-runtime)


#### Konfigurationsfil
Din `Dockerfile` kan innehålla samma saker som i guiden "Dockerize Vue app" ovan.

Följande guide utgår från [Building Docker Images with heroku.yml](https://devcenter.heroku.com/articles/build-docker-images-heroku-yml)

Skapa en ny fil med namnet `heroku.yml` och följande innehåll:
```
build:
 docker:
   web: ./Dockerfile
```

Idén är att Heroku ska publicera nya versioner av appen automatiskt, när vi pushar till master på GitHub. Yml-filen talar om för Heroku att den ska använda Dockerfile för att bygga nya versioner av appen.

Du behöver ansluta Heroku till repot. Gå till [Heroku Dashboard](https://dashboard.heroku.com/apps/), fliken **Deploy**. Som *Deployment method* ska du välja **GitHub** i stället för *Container Registry*. När det står *App connected to GitHub* skrivier du in namnet på GitHub-repot i sökfältet och kopplar ihop repot med Heroku. Längst ner på sidan kan du slå på **Automatic Deploys**. Klicka på **Deploy Branch** för att se till så att Heroku tar emot och börjar bygga repot.

Nu kan du klicka på *Overview* fliken för att kontrollera att Heroku hämtar och bygger appen till en image-fil. När bygget är klart kan du öppna appen i en ny webbläsarflik.

#### Dyno
Oavsett vilket alternativ du väljer, så måste Heroku ha resurser för att kunna köra appen. Under fliken *Overview* står det *Dyno formation*. Kontrollera att det står `web http-server dist/ - ON`. (Om du använde nginx så ser början på raden annorlunda ut.) Om det står **Off** så behöver du ändra genom att klicka på *Configure Dynos*. Klicka på pennan för att kunna slå på eller av. Glöm inte att spara. Om du har använt flera images tidigare så behöver bara den som du kör för tillfället ha en dyno tilldelad till sig.
