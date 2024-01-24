# 2. Observeren

## 2.1 Technologische Methoden

### User-Agent String Detection
User-Agent String Detection:
Server-side device detection vaak door analyse van de HTTP request headers, specifiek de User-Agent string.
Dit kan effectief zijn omdat het onmiddellijk de identiteit van het apparaat bepaalt bij het maken van de
request, waardoor de server alleen de meest geschikte media en content kan
leveren [¹](https://webplatform.github.io/docs/concepts/Detecting_device_and_browser/) [²](https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent).
- **Voordelen:** Bespaart client resources; geen aanpassing van de content door de client nodig; mogelijkheid
  tot optimalisatie van assets [¹](https://webplatform.github.io/docs/concepts/Detecting_device_and_browser/).
- **Nadelen:** Vereist frequente updates van databases; niet altijd accuraat; reageert niet op
  gebruikersinstellingen [¹](https://webplatform.github.io/docs/concepts/Detecting_device_and_browser/).

### Client-Side Feature Detection
Maakt gebruik van JavaScript om het type browser en functies te detecteren met behulp van DOM-objecten en
eigenschappen zoals `screen.width`, `screen.pixelDepth`, `navigator.userAgent`, en `navigator.cookieEnabled` [¹](https://webplatform.github.io/docs/concepts/Detecting_device_and_browser/) [²](https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent).

- **Voordelen:** Kan snel reageren op specifieke clientcondities; geen server-side device database nodig; handig voor real-time aanpassingen [²](https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent).
- **Nadelen:** Kan leiden tot het aanvragen van niet-ondersteunde content; volledige pagina moet mogelijk
  worden gedownload voordat scripts het DOM kunnen manipuleren; niet ondersteund op sommige oudere
  apparaten [²](https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent).

### Gecombineerde Detectie
Een gecombineerde aanpak van server-side en client-side detectietechnieken kan de ontwikkelaar in staat
stellen alleen content te leveren die wordt ondersteund door het apparaat, terwijl de browser stijl en
lay-out kan aanpassen op basis van de huidige context [¹](https://webplatform.github.io/docs/concepts/Detecting_device_and_browser/).

- **Voordelen:** Kan de sterke punten van beide methoden benutten; verhoogt de nauwkeurigheid van de detectie.
- **Nadelen:** Kan complexer zijn om te implementeren en vereist grondig testen om effectief te zijn.

Deze informatie vormt de basis voor een gedegen benadering van apparaatdetectie die essentieel is voor het aanpassen van webcontent aan verschillende apparaten, waaronder eReaders.

---

## 2.2 Marktanalyse

### 2.2.1 Demografische Trends
De eReader-markt toont een sterke vrouwelijke meerderheid onder lezers, met een geslachtsverhouding van 64% vrouwelijk tegenover 36% mannelijk. De gemiddelde leeftijd van lezers is 44 jaar, wat aangeeft dat de markt een volwassen demografie aantrekt die waarde hecht aan het gemak en de draagbaarheid van eReaders [³](https://www.zippia.com/reader-jobs/demographics/).

- **Voordelen:** Een gerichte benadering van marketingstrategieën voor deze demografische groep kan leiden tot hogere conversies en klantentrouw.
- **Nadelen:** Er kan een minder sterke vraag zijn vanuit jongere demografieën die meer geneigd zijn tot het gebruik van smartphones en tablets voor leesdoeleinden.

### 2.2.2 Kansen in de Markt
Met een verwachte marktomvang van USD 16.42 miljard in 2023 en een CAGR van 4.78% tot 2028, biedt de eReader-markt substantiële kansen, vooral in de Azië-Pacific regio die naar verwachting het snelst zal groeien. Verder stimuleert de opkomst van verbonden apparaten en digitale educatie de vraag naar eReaders, wat nieuwe mogelijkheden creëert voor markttoetreders.

- **Voordelen:** Toenemende marktgroei door technologische vooruitgang en de groeiende neiging

tot digitale educatie en zelfpublicatie.
- **Nadelen:** Concurrentie van smartphones en tablets, die ook dienstdoen als leesapparaten.

### 2.2.3 Technologische Ontwikkelingen
Technologische innovaties, zoals waterbestendigheid, verbeterde connectiviteit en kleuren e-ink schermen, dragen bij aan de aantrekkelijkheid van eReaders. De focus van fabrikanten op R&D en nieuwe productlanceringen, zoals de BOOX Poke2 en iReader C6, benadrukken de dynamiek van de markt [³](https://www.zippia.com/reader-jobs/demographics/).

- **Voordelen:** Innovaties leiden tot verbeterde gebruikerservaringen en uitbreiding van de markt.
- **Nadelen:** Hoge kosten voor technologische ontwikkeling en snelle veroudering van producten.

Deze analyse geeft inzicht in de complexiteit van de eReader-markt en belicht factoren die van invloed zijn op de groei en acceptatie van eReaders wereldwijd.

<seealso>
    <category ref="ref">
        <a href="https://webplatform.github.io/docs/concepts/Detecting_device_and_browser/" id="1">1. WebPlatform Docs. (n.d.). Device and browser detection. Retrieved from https://webplatform.github.io/docs/concepts/Detecting_device_and_browser/</a>
        <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent">2. Mdn Web Docs. (n.d.). Browser detection using the user agent. Retrieved from https://developer.mozilla.org/en-US/docs/Web/HTTP/Browser_detection_using_the_user_agent</a>
        <a href="https://www.zippia.com/reader-jobs/demographics/">3. Zippia. (2023). Reader Demographics and Statistics [2023]: Number Of Readers In The US. Retrieved from https://www.zippia.com/reader-jobs/demographics/</a>
    </category>
</seealso>

