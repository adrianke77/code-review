# Code Review for Yi Sheng's Exploding Kitten Game

## Project Repo

https://github.com/yisheng90/GA-Project-1-The-Exploding-Kitten-

## Review

#### Project Purpose

The project is a browser-playable version of the Exploding Kittens card game, which pits the player against one AI enemy.

#### Project Organization

The project's logic is split into five components:

a) Cards.js, which encapsulates the attributes and functions of the eight different card types in the game; this includes the constructors and methods for each card.

b) Player.js, which encapsulates the Player object constructor and methods for the player playing his card, and drawing a card.

c) Game.js, which encapsulates the Game constructor which stores game misc trackers such as number of turns, the cards in each location(player hand, drawingPile, etc), methods for game misc functions (whoWon,restart,startGame etc) and two methods for shuffling and reinsterting exploding Kitten cards.

d) ComputerAI.js, which encapsulates the logic chain the computer AI (player 1) runs through on its turn. It uses a weighted system to decide what action to take next depending on the current situation(what was the player's last move, no of cards player has left,moves left etc )

e) main.js, which encapsulates DOM manipulation, including dynamic positioning of divs that represent cards and so on

In additional, index.html contains all the divs used for various game elementss and starting CSS class labels, and style.css contains div sizing, initial positioning, coloring, references to images and so on.

A img subdirectory contains images for all cards, game elements and so on; a sound subdirectory contains the bomb exploding and cat meow sound effects.

#### Features

* A full implementation of all the game mechanics from the Exploding Kitten card game, including some rather difficult to implement card actions
  
* A full computer AI that makes diecisions based on weighting and takes into consideration a large amount of available info, even including the number of the opponent's cards and his most recently played cards.

#### Areas of Success (Code, Organization)

* Very well organised
    - the encapsulations are logical and game elements and mechanics correspond well to components in the code
    - everything is generally neat and readable
* Remarkable amount of functionality
    - all card actions are implemented and a fully working AI that takes a large amount of information into consideration for actions
* Appealing external design
    - appealing graphics, sound and display layout

#### Areas for Improvement (Code, Organization)

* May want to consider wrapping the contents of main.js in an object constructor to fully isolate the variables from the global namespace - although not neccessary for the project, it may be a good habit as a coding approach.

* A difficulty selector based on having high randomness() (used for making the AI behave more erratically/less reliably) might be a nice touch: high randomness for lower difficulty levels and low/no randomness for highest difficulty levels 

## Additional Notes

Would be interesting to consider how much additional work would allow a multiplayer game where each player can either be human or AI... hehehe
