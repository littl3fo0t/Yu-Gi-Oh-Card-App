# Yu-Gi-Oh! Card Searching App
This is a simple app to search and retrieve the card details from the **Yu-Gi-Oh! Trading Card Game** using the [YGOPRODeck API](https://ygoprodeck.com/api-guide/) and styling done using [Bulma CSS](https://bulma.io/).

This project idea came to me after completing the **Learn Intermediate JavaScript** course from the [Codecademy](https://www.codecademy.com/) website. I wanted to build a simple web app using vanilla JavaScript **before** eventually re-creating it using React at a later date to compare and contrast the developer experience of building both apps.

## Why Yu-Gi-Oh?
As a fan of the TCG and an active player on **Yu-Gi-Oh! Master Duel** (the online version of the game), I just thought it would be a fun way of incorporating something I like into this project. On a more practical level, Yu-Gi-Oh cards are divided into 3 main categories (Spell, Trap and Monster Cards), all having both shared and unique properties, which seemed perfect to test my newly acquired knowledge of JavaScript.

## Yu-Gi-Oh! Card Properties
Below are the relevant card properties by category:

1. Spell/Trap Cards:
    * Card Name - The name displayed on the card.
    * Card Type - The type of Spell/Trap card (eg: Field, Equip, Counter, Normal etc).
    * Card Text - The text displayed on the card.
2.  Monster Cards:
    * Card Name - The name displayed on the card.
    * Card Type - An array of types that correspond to the monster card (eg: Fiend, Machine, Effect, Fusion etc).
    * Attribute - The attribute of the monster (eg: DARK, LIGHT, EARTH etc).
    * Card Frame - The backdrop type that the card uses (normal, effect, synchro, xyz etc).
    * Level - Between 1 and 12 (**not** applicable to Link and XYZ monsters).
    * Rank - Between 0 and 13 (**only** applicable to XYZ monsters).
    * Link Rating - Between 1 and 6 (**only** applicable to Link monsters).
    * ATK - Attack stat of the monster.
    * DEF - Defense stat of the monster (**not** applicable to Link monsters).
    * Pendulum Scale - The Pendulum Scale of the monster (**only** applicable to Pendulum monsters).
    * Pendulum Effect - The text printed in the Pendulum Effect area of the card (**only** applicable to Pendulum monsters).
    * Card Text - The text displayed on the card.

## Getting Started
There are **no** dependencies required for this project, all you need to do is to download the `index.html` file and open it in any browser.

## Using the App
Once opened in a broswer, all you need to do is enter the **exact** card name for which you want to retrieve the details off in the search bar:
![Screenshot of UI on first page load](./images/UI-On-Page-Load.png)

Once done, you can click on the Submit button to retrieve and display the card details. For example, searching for the spell card "Called by the Grave" will produce the following output:
![Sample output for spell card search](./images/sample-spell-card-output.png)

Since monster cards contain more details, they will be displayed as such:
![Sample output for monster card search](./images/sample-monster-card-output.png)

### Error Checking
The app does perform some simple form of input validation and will render an error message in case of invalid card name:
![Output for missing card name](./images/sample-missing-card-name-error.png)
![Output for invalid card name](./images/sample-invalid-card-name-error.png)

### App Limitations
1. As mentioned above, you are required to enter the **exact** card name in order for the app to properly retrieve the data. The YGOPRODeck API does support fuzzy name search and searching by other properties such as the card type, attack stat and much more. As such, when I re-create the app using a web framework, I would like to enable support to search by multiple properties.
2. A major aspect of the appeal of Yu-Gi-Oh! is the art of the cards, however, while the YGOPRODeck API does return an array of image URLs, as per the API notes, you are **not** expected to hotlink images directly from the website, least you risk your IP address being blacklisted by them. I did think about displaying a generitic card image where the frame would match the one of the searched card. However, there are so many possible card frame in Yu-Gi-Oh! (especially when you consider Pendulum cards), that I quickly dropped the idea.
3. Using vanilla JavaScript means that I have no way of automatically binding my HTML to my code and instead need to imperatively grab the DOM elements:
```js
// Get DOM elements
const monsterCardDetails = document.querySelectorAll("tr.monsterCardDetails");
const name = document.getElementById("cName");
const attribute = document.getElementById("cardAttribute");
const level = document.getElementById("cardLevel");
const atk = document.getElementById("cardATK");
const def = document.getElementById("cardDEF");
const pScale = document.getElementById("pScale");
const pendulumEffect = document.getElementById("pendulumEffect");
const type = document.getElementById("cardType");
const cardText = document.getElementById("cardText");
```
This obviously will not scale very well in the longterm and is something I hope to address when using a web framework.

## Author
Thomas Brun - [@littl3fo0t](https://github.com/littl3fo0t)