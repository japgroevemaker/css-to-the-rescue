# CSS-TO-THE-RESCUE

Omdat ik een groot fan ben van Elvis Presley, wilde ik graag een website maken die in het teken van Elvis staat. Het moest een pleasureable website worden, waar ook makkelijk doorheen te tabben was.

[Live demo](https://japgroevemaker.github.io/css-to-the-rescue/styleguide.html)

## Eisen

-   [x] Geen classes gebruiken
    -   Het doel was om geen classes te gebruiken binnen deze website en de elementen alleen aan te roepen via hun `HTML` tagname.


-   [ ] Geen `id's` gebruiken
    -   Het was ook een vereiste om geen `id's` te gebruiken, dit is helaas niet helemaal gelukt. Ik roep ze dan weliswaar niet aan, maar ik heb `id's` nodig om de checkboxen via de labels te kunnen checken. Dat ziet er dan zo uit.
    ```html
    <input type="checkbox" id="Chat">
    <label for="Chat"><img src="image/chat.svg" alt="chat"/></label>
    ```


-   [x] Werken met `display: grid;` en `display: flex;`
    -   Met `display: flex;` werk ik wel vaker en dat werkt erg fijn. Dit was de eerste keer dat ik met `display: grid;` heb gewerkt, en het werkt erg fijn kan ik je vertellen. Het was even wennen qua hoe je de element in het `grid` indeeld, maar als je het eenmaal onder de knie hebt dan gaat het vanzelf.


-   [x] Fancy ampersand
    -   Er moest ergens in de site een fancy ampersand zitten. Deze heb ik in de header toegevoegd.
    ```html
    <h1>Elvis <span>&amp</span> you</h1
    ```


-   [x] De - emphasize by dimming

    -   Ik moest er ook voor zorgen dat er ergens in de website iets gedimdt werd op commando. Dit heb ik toegevoegd als men op de chat button klikt.

    ```css
    div {
      position: fixed;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, .8);
      bottom: -100em;
      left: 0;
      right: 0;
      z-index: 20;
      filter: blur(100em);
      transition: bottom 0.2s;
    }
    ```

-   [x] Intrinsic sizing

    -   Intrinsic sizing houdt zijn waardes die je een `HTML` element geeft zodat hij zich min of meer naadloos aanpast aan zijn parent element. De Intrinsic sizing heb ik zo toegepast:

    ```css
    article {
      width: fit-content;
    }
    ```

-   [x] Styling by sibling count

    -   Styling by sibling count is het selecteren en stijlen van html element door ze individueel te selecteren zonder er een `class` of `id` aan te geven. Ik heb dit op veel plaatsen toegepast, en het is super makkelijk te gebruiken!

    ```css
      section>a>article>h2:nth-of-type(1) {
        width: 6em;
        margin: 0.2em auto;
      }
    ```

-   [x] Vertical centring
    -   Horizontaal centreren is makkelijk door een element `margin: auto;` te geven of door `text-align: center` op een parent element te zetten. Maar verticaal centreren is andere koek. Er zijn een aantal manier om dit toe te passen. Ik heb het gedaan door `position: fixed;` op een element te plaatsen om vervolgens de `top` en `bottom` waarde allebei op `50%` te zetten. Hierdoor komt hij perfect verticaal gecentreerd in beeld.


-   [x] Transition op `hover` en `focus`
    -   Om mijn site zo pleasureable mogelijk te maken, heb ik `transitions` toegevoegd op verschillende elementen als de gebruiker er over heen `hovert` of als er op dat element `gefocust` wordt. Hier een klein voorbeeld:
    ```css
    footer > label:hover {
      transform: scale(1.10, 1.10);
      transition: all 0.2s;
    }
    ```

- [x] Custom checkbox
  - Een opdracht was het maken van een custom checkbox. De ```input type="checkbox"``` moet je als eerst een ```opacity: 0;``` geven. Daarna kan je het ```label``` element gaan stijlen en er een eigen checkbox van maken.
  ```css
      input[type="checkbox"]:checked+label::before {
          transform: scale(1.01, 1.01);
          content: '✔';
          color: var(--link-color);
          border: solid 0.1em var(--link-color);
          font-size: 1.2em;
          height: 1.2em;
          width: 1.2em;
          text-align: center;
          transition: all 0.2s;
          -webkit-animation: rubberBand 0.65s;
          animation: rubberBand 0.65s;
        }
        ```


    - [x] Validatie van het formulier
     - Een vereiste was ook dat ik het formulier zou stijlen en de gebruiker feedback zou geven over hun geleverde input. Dit heb ik gedaan doormiddel van ```input:valid``` en ```input:invalid```. Op deze manier kan je de gebruiker makkelijk feedback geven over het geen wat hij/zij nog moet verichten om het formulier compleet te maken.


    ## Bronnen
    - Rating example makes use of Emoji from: http://emojione.com
    - Stijlen van het ```<progress>``` https://www.hongkiat.com/blog/html5-progress-bar/
