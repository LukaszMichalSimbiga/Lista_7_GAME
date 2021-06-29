# Lista_7_GAME
## Autor
Łukasz Michał Simbiga
## Introduction
Do you also think that the standard TIC TAC TOE play is too simple?
Then I think that this version will be more interesting.
## Technologies
In this project I use:
* Python 3.7.9
* tkinter 8.6
## Instruction
* To play this game you have to click "Start new game" button in game menu. 
* Next you must click on new window with orange grid in the center.
* Orange box shows the current selection location.
* With numbers on the keyboard we make a movement/selection.
* [1,2,3,4,5,6,7,8,9] are appropriately left-down , down , right-down , left , center , right , left-up , up , right-up
* Win in block(big) change block(big) in circle if circle win , or in cross if cross win inside of this block(big).
* Your choose determines the block(big) in which the opponent have to make the next move.
* If this block(big) is change in symbol. Opponent can make next move everywhere (choose block(big) and next choose field in this block ).
* If block(big) is full but no one win in this block(big) then block(big) cleans up.
* If war mod is off the game is over when there is no more moves or if somebody arrange tree of his symbosy in a row in blocks(bigs).
* If war mod is on the game is over when there is no more moves or someone's health bar drop to 0.
* In war mod everyone have 10 lives.
* If someone win in war mad. Damage to enemy health bar is equal to numbers of blocks(big) not changed to symbols.
## How to run this game
1. Clone the template project, replacing my-project with the name of the project you are creating: 
`https://github.com/LukaszMichalSimbiga/Lista_7_GAME.git my-project`
`cd my-project `
2. Install the project's development and runtime requirements:
`pip install -r requirements.txt`
