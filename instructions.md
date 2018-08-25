                                                    Around the Board

The Around the Board project is a flexbox practice project. You will have no css folder or file so you will start this from scratch. Before you place any javascript on the page your job is to build the board to detail as follows:



Once you completed this begin by creating a javascript file and allow the user to click on the dodecahedron dice, the dice should roll, display a number, then move the players pieces accordingly. You will not need to add more to this you just simply need to complete the assignment and have every player move around the board without throwing any errors. 

Note: There is a javascript file also already in the project folder. That contains a function called getSpots. This function’s purpose is to return an array that orders the divs with class “spots”, when the dice is rolled you can move to the appropriate place based on the number you rolled.

The instructions are as follows:

1.Create a CSS folder and a CSS file. Make sure you have linked to your HTML file.

2.Create a div with a class board. Use CSS to position it absolutely so that the top and bottom margin is always 10%        of the viewport height and left and right margins are 10% of the viewport width. Give it a border of 8px solid black.

3.Create your four quadrants by creating four divs and give them a class of row AND classes of south, west, north, and      east in that order.Use position absolute on these divs and set the positions based on which quadrant they are suppose     to be positioned (use top, left, right, bottom as needed). You can give each one of these divs a border for now so you    can set there appropriate size. They should touch each either in a similar way just like in the picture. 

4.Now inside of each one of these quadrants, create child divs with the class spots. The amount of child divs should be     as followed for each quadrant: South: 7 child divs, West: 4 child divs, North: 7 child divs, East: 4 child divs. You      need to make each one of these divs have the same size, except the first child of each quadrant. Add another class to     each one of these child divs, so that you can separately create a size that will fit accordingly to how the picture is    set. 

5.Try and center the dodecahedron dice in the center of the board as you see in the picture. Then center the div with the   class roll in the center of the die. Also, resize so it fits without touching any of the “spot” divs. 

6.In the first child div of the “south” quadrant, create four divs with a class “player”. Also, for each div give each      another class and give them, based on order from top to bottom, class names of “player1”, “player2”, “player3”, and       “player4” respectively.

7.In the javascript file you created, first select the elements that represent the die, the number you roll, and the die    image itself. Create an array of objects that have four elements inside. In each object in this array they should have    two properties. The first property is called player who’s value should be the HTML element for the corresponding          player. The second property should be location that should be set to 0 initially and should remain a number data type.    Make another variable called numPlayers that holds the number of players, a variable called turned and set to zero, a     variable called maxRoll that holds the maximum amount a player can roll, and a variable called maxSpots that is set to    the length of the array returned by the getSpots function minus 1 (since its an array)

8.On the die element container add an event listener that is listening for a click, and calls a function called rollDie.    Create this rollDie function and console.log(“Running rollDie”) to ensure that the function is running properly when I    click on the element. 

9.Inside the rollDie function, first set the textContent of the “roll” element to an empty string. Next, take the src of    the image and set it to the dodecahedron gif, that when you click on the die it displays the gif and looks like the die   is rolling. Use the setTimeout function and make it wait for 1700 milliseconds (this is roughly how long it takes for     the gif to stop moving). Now inside the setTimeout function, create a variable called num that is the value of a          randomly generated number multiplied by the maxRoll variable then rounded. Set the textContent of the roll element to     the value of num, then call the movePlayer function and the changeTurn function. Create these function outside of the     scope of the rollDie function so you do not run into any errors.

10.Before you continue to the movePlayer function, return to the call of the movePlayer function in the rollDie function    and pass in two values as parameters. The first should be the num variable that you create inside the rollDie function    and the second should be a call to the getSpots function (remember its purpose is to return an array). Now in the         movePlayer function add two parameters and call the first one num and the second one spots. Inside the function, grab     the current players location by first referencing the players array and using the turn variable to select the correct     element in the array, then increment the value by the value of the num variable. Now select the element inside the        spots array by referencing the location of the player that is currently playing, then append the player HTML element to   the selected spot (Hint: use element.appendChild)

11.Your final function you need to create was the changeTurn function. In this function you simply need to increment the    turn variable so you can cycle through each player playing the game. Make sure when the turn variable becomes greater     than maxPlayers set the value back to zero.

12.Now to finish of this app, go back to the movePlayer function. You will see that if you play til you reach the east      quadrant and roll enough to go around the board you will reach an error. That’s because you need to reference the south   quadrant and the numbers to do so are 0 - 6. So if the players location gets greater than maxSpots minus the newly        incremented location property of each player by the number of spots on the board. This will correct the error. 