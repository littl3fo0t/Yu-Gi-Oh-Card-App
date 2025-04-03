# Yu-Gi-Oh! Card Searching App
This is a simple app to search and retrieve the card details from the **Yu-Gi-Oh! Trading Card Game** using the [YGOPRODeck API](https://ygoprodeck.com/api-guide/) and styling done using [Bulma CSS](https://bulma.io/).

This project idea came to me after completing the **Learn Intermediate JavaScript** course from the [Codecademy](https://www.codecademy.com/) website. I wanted to build a simple web app using vanilla JavaScript **before** eventually re-creating it using React at a later date to compare and contrast the developer experience of building both apps.

## Why Yu-Gi-Oh?
As a fan of the TCG and an active player on **Yu-Gi-Oh! Master Duel** (the online version of the game), I just thought it would be a fun way of incorporating something I like into this project. On a more practical level, Yu-Gi-Oh cards are divided into 3 main categories (Spell, Trap and Monster Cards), all having both shared and unique properties, which seemed perfect to test my newly acquired knowledge of JavaScript.

### Yu-Gi-Oh! Card Properties
Below are the relevant card properties by category:

1. Spell/Trap Cards:
    * Card Name - The name displayed on the card
    * Card Type - The type of Spell/Trap card (eg: Field, Equip, Counter, Normal etc)
    * Card Text - The text displayed on the card
2.  Monster Cards:
    * Card Name - The name displayed on the card
    * Card Type - An array of types that correspond to the monster card (eg: Fiend, Machine, Effect, Fusion etc)
    * Attribute - The attribute of the monster (eg: DARK, LIGHT, EARTH etc)
    * Card Frame - The backdrop type that the card uses (normal, effect, synchro, xyz etc)
    * Level - Between 1 and 12 (**not** applicable to Link and XYZ monsters)
    * Rank - Between 0 and 13 (**only** applicable to XYZ monsters)
    * Link Rating - Between 1 and 6 (**only** applicable to Link monsters)
    * ATK - Attack stat of the monster
    * DEF - Defense stat of the monster (**not** applicable to Link monsters)
    * Pendulum Scale - The Pendulum Scale of the monster (**only** applicable to Pendulum monsters)
    * Pendulum Effect - The text printed in the Pendulum Effect area of the card (**only** applicable to Pendulum monsters)
    * Card Text - The text displayed on the card