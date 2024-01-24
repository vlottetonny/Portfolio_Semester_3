Mijn project wordt door sonarcloud gescanned wanneer er naar dev gepushed wordt, Eslint zit in de IDE waarin ik het heb gemaakt, en typesafety wordt overal geverifieerd.
Alle tests zijn gedaan met het jest framework

**Backend**

In de back-end voer ik tests uit om ervoor te zorgen dat de kwaliteit en betrouwbaarheid gecontroleerd en aangetoond kan worden. Dit is belangrijk 
om te verifiëren of alles naar verwachting werkt. Maar ook om dit in een professionele setting te kunnen bewijzen.

Hier leg ik een van de tests uit om te laten zien hoe het in zijn werk gaat. Deze test voert een get code operatie uit waarbij een lijst van code, en een 200 response
moet worden teruggegeven.

    describe('code.controller', () => {
        describe('getCode', () => {
         it('should return a code and return 200 on success', async () => {
              // Arrange
              const req = {} as Request;
              const res = {
                status: jest.fn(() => res),
                send: jest.fn()
              } as unknown as Response;
              (codeService.getCode as jest.Mock).mockResolvedValue('1234');

              // Act
              await codeController.getCode(req, res);

              // Assert
              expect(res.status).toHaveBeenCalledWith(200);
              expect(res.send).toHaveBeenCalledWith('1234');
        });
    });

**Structuur**

- **Arrange**
In de arrange sectie worden de noodzakelijke variabelen en objecten aangemaakt
die nodig zijn om informatie uit de get code te halen. De andere applicatie lagen worden gemocked
- **Act** Vervolgens wordt in de Act sectie de Get code controller call uitgevoerd. 
- **Assert** In de Assert sectie wordt het resultaat vergelegen met de het verwachte resultaat

**Frontend**

In de frontend voeren we tests uit om de functionaliteit en betrouwbaarheid van de gebruikersinterface te controleren. Dit is cruciaal om te verifiëren of de gebruikerservaring soepel verloopt en om de kwaliteit van de software in een professionele omgeving te waarborgen.

Hieronder leg ik een van de tests uit om te laten zien hoe het in zijn werk gaat. Deze test controleert of de juiste inhoud wordt weergegeven op basis van de user agent van de gebruiker.

```typescriptreact
describe('Home Page', () => {
    let userAgentSetter: jest.SpyInstance;

    beforeEach(() => {
        userAgentSetter = jest.spyOn(window.navigator, 'userAgent', 'get');
    });

    afterEach(() => {
        userAgentSetter.mockRestore();
    });

    it('shows the e-reader site when user agent is an e-reader', () => {
        userAgentSetter.mockReturnValue('Kindle');
        const { getByText } = render(<Home />);
        expect(getByText('E-Reader')).toBeInTheDocument();
    });

    it('shows the no e-reader site when user agent is not an e-reader', () => {
        userAgentSetter.mockReturnValue('Mozilla');
        const { queryByText } = render(<Home />);
        expect(queryByText('E-Reader')).not.toBeInTheDocument();
    });
});
```

**Structuur**

- **Arrange**
  In de arrange sectie wordt de user agent gemocked om verschillende scenario's te simuleren. In dit geval wordt de user agent ingesteld op 'Kindle' om een e-reader te simuleren en op 'Mozilla' om een niet-e-reader te simuleren.

- **Act**
  Vervolgens wordt in de Act sectie de Home component gerenderd. Dit simuleert het laden van de pagina door de gebruiker.

- **Assert**
  In de Assert sectie wordt gecontroleerd of de juiste inhoud wordt weergegeven op basis van de user agent. Als de user agent een e-reader is, wordt verwacht dat de tekst 'E-Reader' aanwezig is. Als de user agent geen e-reader is, wordt verwacht dat de tekst 'E-Reader' niet aanwezig is.

