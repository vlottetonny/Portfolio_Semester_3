# EpubTransmitter

    - [5.1 De aanpak](#51-de-aanpak)
    - [5.2 De stackkeuze](#52-de-stackkeuze)
    - [5.3 User stories](#54-user-stories)
    - [5.3 De uitvoering](#54-de-uitvoering)
    - [5.4 Gebruikers testen](#54-gebruikers-testen)
Dit project is een NextJs applicatie met een ExpressJS backend. De applicatie is ontworpen om gebruikers in staat te stellen hun eReader te verbinden met hun laptop of telefoon. Door de applicatie op beide apparaten te openen, genereert de eReader een willekeurige code die de gebruiker vervolgens op hun laptop of telefoon kan invoeren om de apparaten te koppelen. Zodra de apparaten zijn gekoppeld, kan de gebruiker een EPUB-bestand uploaden naar de backend. Dit bestand wordt tijdelijk opgeslagen in een MongoDB-database voordat het naar de eReader wordt gestuurd.

## 5.1 De aanpak

## 5.2 De stackkeuze
In dit hoofdstuk bespreek ik de frameworks en technologieën die ik heb gekozen voor dit project. Ik leg uit waarom ik deze heb gekozen en wat de voor- en nadelen zijn. Voor zowel de frontend als de backend heb ik gekozen voor een framework dat is gebaseerd op JavaScript. Dit is een goede keuze omdat het betekent dat ik de applicatie in één taal kan schrijven. Dit maakt het makkelijker om de applicatie te maken en te onderhouden. Ik heb ook TypeScript gebruikt om de applicatie te schrijven. Dit is een goede keuze omdat het betekent dat ik de applicatie kan schrijven met de voordelen van TypeScript, zoals type checking en code completion.

### 5.2.1 NextJs
Voor de frontend van het EpubTransmitter project is gekozen voor NextJs. Dit is een React framework dat het mogelijk maakt om een React applicatie te maken die server-side gerenderd wordt. Dit is een goede keuze voor dit project omdat het de mogelijkheid biedt om de applicatie te laten werken zonder JavaScript. Dit is belangrijk omdat eReaders vaak geen JavaScript ondersteunen. Door de applicatie server-side te renderen, kan de gebruiker de applicatie gebruiken zonder JavaScript. Als de gebruiker JavaScript heeft ingeschakeld, wordt de applicatie client-side gerenderd, wat een betere gebruikerservaring oplevert.

### 5.2.2 ExpressJS
Voor de backend van het EpubTransmitter project is gekozen voor ExpressJS. Dit is een NodeJS framework dat het mogelijk maakt om een NodeJS applicatie te maken die een API aanbiedt. Dit is een goede keuze voor dit project omdat het de mogelijkheid biedt om een API te maken die de applicatie kan gebruiken om bestanden te verzenden. De API is nodig omdat de applicatie niet direct bestanden kan verzenden naar de eReader. De API is nodig om de bestanden op te slaan en te verzenden naar de eReader.

### 5.2.3 MongoDB
Voor de database van het EpubTransmitter project is gekozen voor MongoDB. Dit is een NoSQL database die het mogelijk maakt om documenten op te slaan. Dit is een goede keuze voor dit project omdat het de mogelijkheid biedt om de bestanden op te slaan in een database. De database is nodig omdat de applicatie de bestanden moet opslaan voordat ze naar de eReader worden verzonden. De database is nodig om de bestanden op te slaan en te verzenden naar de eReader.

## 5.3 User stories
**As a reader i want to be able to upload a file to my e-reader from my phone or laptop to avoid having to use an annoying cable.**
