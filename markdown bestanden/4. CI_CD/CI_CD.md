Het Continuous Integration/Continuous Deployment (CI/CD) proces in dit project is geconfigureerd om te werken met de Dockerfile in de root van het project. Hier is een kort overzicht van hoe het werkt:  
Continuous Integration (CI): Wanneer er wijzigingen worden gepusht naar de hoofdbranch van de repository, wordt er een nieuwe Docker image gebouwd. Dit wordt gedaan door de instructies in de Dockerfile te volgen. De Dockerfile begint met het specificeren van de basis image (node:18), stelt de werkdirectory in op /app, kopieert de package.json naar de werkdirectory, installeert de npm-afhankelijkheden, kopieert de rest van de code naar de werkdirectory, stelt de poort in die moet worden blootgesteld (8000) en specificeert het commando dat moet worden uitgevoerd wanneer de container wordt gestart (npm start).  
Continuous Deployment (CD): Nadat de Docker image succesvol is gebouwd, wordt deze naar een Docker registry gepusht. Van daaruit kan het worden gedeployed naar de productieomgeving. Het specifieke proces voor het deployen van de image hangt af van de gebruikte infrastructuur en deployment tools.  
Dit is een basisoverzicht van het CI/CD-proces zoals het momenteel is geconfigureerd. Afhankelijk van de specifieke tools en services die worden gebruikt, kunnen er extra stappen of configuraties nodig zijn.

In de frontend van het epubtransmitter project hebben we een CI/CD-pijplijn opgezet met behulp van GitHub Actions. De configuratie hiervan is te vinden in het bestand .github/workflows/docker-image.yml.  Bij elke push of pull request naar de main branch, wordt een workflow gestart. Deze workflow bestaat uit verschillende stappen:  
De code wordt uitgecheckt met behulp van de actions/checkout@v3 actie.
Vervolgens worden de afhankelijkheden geïnstalleerd met npm install.
Daarna worden de tests uitgevoerd met npm test.
Als alle tests slagen, wordt de Docker image gebouwd met het commando docker build . --file Dockerfile --tag vlottetonny/epubtransmitterfrontendgithub:${{ github.sha }}.
Daarna loggen we in op Docker Hub met de opgeslagen Docker Hub-gebruikersnaam en -wachtwoord in de GitHub Secrets.
Ten slotte, als alle voorgaande stappen succesvol zijn uitgevoerd, wordt de Docker image gepusht naar Docker Hub met het commando docker push vlottetonny/epubtransmitterfrontendgithub:${{ github.sha }}.
De Docker image wordt gebouwd met behulp van een Dockerfile die bestaat uit twee stadia: een bouwfase en een uitvoeringsfase. In de bouwfase wordt de applicatie gebouwd en worden de ontwikkelingsafhankelijkheden verwijderd. In de uitvoeringsfase wordt de gebouwde applicatie uitgevoerd.