# ICEN-150-Final--Simon
This project involved making an arduino game that was similar to the game of Simon. The game of Simon used a red, blue, green and yellow led that flashes in a radom and incrementimg sequence, building off of the last sequence. The user would press the button corresponding to the light and if they got the correct sequence, then the game would increase the sequence. If the user failed to complete the sequence, then the lights would flsh in a certain order, showing that a new game was started. This would be followed by a sequence of sounds. Each light also had its own unique sound. If the button was pressed for a specific light, then the light would illuminate and a sound would be played.


My project uses 4 buttons and LED's for 2 reasons. The first is because it reflected the original game of Simon better, rather than the three buttons that was assigned. I wanted to stay as close to the original game as possible, so I decided to add the fourth button. Before this, I learned that with three buttons, the sequence that the LED's lit up with were less random and seemingly decided to only light up 2 equally, while the third would get up infrequently. If I changed the LED array to four, it seemingly changed the randomness of the outcome to be more widespread.


The hardware was set up so that the LED's would use the even pins, while the corresponding button that accompanied the LED was the folowwing pin on the Arduino. I made the last pin that I would use to be the buzzer pin for simplicity's sake. I ran one ground wire to the arduino and one 5 volt output to the arduino on the rails with the corresponding line (the red line for power and black or blue for ground.) I connected each ground with a short wire to the negative side to the LED and the side on the buzzer that did not have a plus sign on the front. I used a short black cable for this, as seen in the diagrams. I ran each button to a ground, but also connected to a 10k Ohm resistor because I used the button diagram for the Arduino examples for reference. (link) Each button also was connected to the 5 volt rail, also as seen in the button diagram. 


The code used a set of functions. I used setup, input, output, and a play sound. The loop function was never used, but had to be included because it would not run without it present, so I simply opened and closed the function, while leaving it blank. Before the setup, I set my many global variables- my four buttons that I named switches one through four- only because it was a shorter name than button. I also used global variables named led one through four (led1,led2,...etc.) I also named arrays for the random function, level, and for the input.


The setup function sets the LED'S to outputs and the buttons or switches to output, as well as sets the random function, or the randomseed. I found this in the arduino library example, whose link is shown here. (link) It also says that for every level that is less than or equal to 20 to run the input and output functions.


The input function reads the buttons or switches to determine which button is being pressed. It will detect if the button that is being pressed corresponds to the light that was lit up are the same. If they are the same, then it will increment the level, but if the comparison is not the same, then it will go to the lose sequence. It will also be the function that makes the buzzer play a specific sound for each button.


The output function will play a sequence of LED's for every value less than or equal to the level. It will also call a random number from 1 through four. One has to make it go to a number less than for the lowest number and 1 above for the highest number because it is low<x<high and does not include the boundaries. It will also similarly make the buzzer play a specific sound with the led that is being lit up, which is the same sound as the corresponding button. It will then flash the LED for .1 seconds and then wait for the user to put in the sequence.


The fail function will play a sequence of sounds while flashing a certain code. For my game, it will flash each LED on and off 4 times to show that the user lost and that a new game is starting.


Finally, the play tone function will make the buzzer play the sounds that it needs to.
