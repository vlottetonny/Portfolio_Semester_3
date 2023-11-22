# 5. Testen

## 5.1 Expirimenten
### 5.1.1 Experimenten Uitvoeren
Ik begin met het testen van de User-Agent String detectie door mijn website zo in te stellen dat deze verschillende types eReaders herkent. Ik gebruik een lijst van bekende eReader User-Agent Strings en test dit op echte apparaten. Als hieruit blijkt dat er nog onnauwkeurigheden in deze manier van meten zitten, dan voeg ik client-side feature detection toe om te zien of dit de nauwkeurigheid verbetert.

### 5.1.2 Resultaten Analyseren
Tijdens het experiment kijk ik hoe nauwkeurig en snel de website het type apparaat herkent. Ook let ik op veranderingen in de gebruikerservaring, vooral op eReaders.

### 5.1.3 Aanpassingen Maken
Als ik merk dat een methode niet goed werkt, probeer ik deze aan te passen of combineer ik verschillende methoden. Mijn doel is om de perfecte balans te vinden tussen nauwkeurigheid en een goede gebruikerservaring voor eReader-gebruikers.

Dit testproces zal mij helpen om de meest effectieve methode te vinden voor het detecteren van eReaders en om mijn website zo goed mogelijk daarop af te stemmen.

## 5.2 Resultaten
### 5.2.1 Resultaten van de Experimenten
Ik heb de User-Agent String detectie getest op verschillende eReaders en andere apparaten. Hieruit blijkt dat deze methode heel nauwkeurig is. De website herkent alle eReaders die ik heb getest, en geen enkele andere apparaten. Ook is de detectie heel snel, omdat de server de User-Agent String al heeft ontvangen voordat de website wordt geladen. Dit betekent dat de website meteen kan zien of het een eReader is of niet.

```Typescript
useEffect(() => {
        const userAgent = navigator.userAgent;
        if (/Kindle|Nook|Kobo|SonyReader/i.test(userAgent)) {
            setIsEreader(true);
        }
    }, []);
```
De user-agent wordt hier gecheckt zodra de website wordt geladen. Als het een eReader is, wordt de website aangepast zodat deze beter werkt op het apparaat. Dit gebeurt door de volgende code:

```Typescript
return (
    // ...
        {isEreader ? ( {/** EReader version of the website */ } ) : ( {/** Non eReader version of the website */} )}
    // ...
);
```
### 5.2.2 Conclusies Trekken
Ik heb geconstateerd dat met de User-Agent String detectie de website heel goed kan zien of het een eReader is of niet. Dit is heel belangrijk, omdat het betekent dat ik de website zo kan aanpassen dat deze goed werkt op eReaders. Ook is de detectie heel snel, wat betekent dat de website meteen kan zien of het een eReader is of niet. Ik vind het daarom niet nodig om client-side feature detection toe te voegen.