# The Turtle Race Program :-

The turtle race program is a fun and interactive Python script that uses the turtle graphics module to simulate a race between six turtles. Here's a detailed description of how the program works:

# Purpose:
The main purpose of this program is to create a simple betting game where the user predicts which turtle will win a race. The turtles move forward by random distances, making the race unpredictable and exciting.

# Key Features:
- **User Interaction:** The program prompts the user to bet on the turtle they think will win by entering a color.
- **Graphical Simulation:** The race is visually represented using the turtle module, with turtles moving across the screen.
- **Random Movement:** Each turtle moves a random distance in each iteration, adding an element of chance to the game.
- **Result Announcement:** Once a turtle crosses the finish line, the program announces the winning turtle and informs the user if their bet was correct.

# Detailed Workflow

- **Importing Modules:** 

Turtle and Screen are imported from the turtle module to create and control the turtle graphics.
random is imported to generate random distances for turtle movement.

- **Setting Up the Screen:**

A Screen object is created and configured with a specific width and height.
The user is prompted to enter their bet on which turtle will win by selecting a color from a predefined list.

- **Creating Turtles:**

Six turtles are created, each with a unique color.
The turtles are positioned at the starting line, spaced evenly along the y-axis.

- **Starting the Race:**

If the user has entered a bet, the race begins.
A loop runs continuously to move the turtles forward until one of them crosses the finish line.

- **Moving the Turtles:**

Inside the race loop, each turtle moves a random distance between 0 and 10 units.
The program checks if any turtle has crossed the finish line (x-coordinate > 230).

- **Determining the Winner:**

When a turtle crosses the finish line, the race stops.
The color of the winning turtle is compared with the user's bet.
A message is printed to the console, indicating whether the user won or lost their bet and announcing the winning turtle.

- **Ending the Program:**

The screen waits for a click from the user to close, allowing them to see the final race results before the program exits.

# Code description starts from here:

**Import Statements:** 

- from turtle import Turtle, Screen
- import random

~ Turtle and Screen are imported from the turtle module.

~ random is imported to generate random distances for the turtles to move.

**Variables and Screen Setup:**

is_race_on = False
screen = Screen()
screen.setup(width=500, height=400)
user_bet = screen.textinput(title="Make your bet", prompt="Which turtle will win the race? Enter a color: ")
colors = ["red", "orange", "yellow", "green", "blue", "purple"]
y_positions = [-70, -40, -10, 20, 50, 80]
all_turtles = []

- **is_race_on:** A flag to control the race loop.

- **screen:** An instance of the Screen class, representing the screen where the race takes place.

- **screen.setup(width=500, height=400):** Sets up the screen with a width of 500 pixels and height of 400 pixels.

- **user_bet:** Captures the user's bet through a text input dialog.

- **colors:** A list of colors for the turtles.

- **y_positions:** A list of y-coordinates for positioning the turtles at the start.

- **all_turtles:** An empty list to store the turtle objects.

# Creating Turtles:

for turtle_index in range(0, 6):
    new_turtle = Turtle(shape="turtle")
    new_turtle.penup()
    new_turtle.color(colors[turtle_index])
    new_turtle.goto(x=-230, y=y_positions[turtle_index])
    all_turtles.append(new_turtle)

- A loop runs from 0 to 5 to create six turtles.

- **new_turtle = Turtle(shape="turtle"):** Creates a new turtle with the shape of a turtle.

- **new_turtle.penup():** Lifts the pen so the turtle doesn't draw lines as it moves.

- **new_turtle.color(colors[turtle_index]):** Sets the color of the turtle from the colors list.

- **new_turtle.goto(x=-230, y=y_positions[turtle_index]):** Positions the turtle at the starting line with the specified y-coordinate.

- **all_turtles.append(new_turtle):** Adds the new turtle to the all_turtles list.

# Starting the Race:

- if user_bet:
    is_race_on = True

If the user has made a bet, the race starts by setting is_race_on to True.

- Race Loop:

while is_race_on:
    for turtle in all_turtles:
        if turtle.xcor() > 230:
            is_race_on = False
            winning_color = turtle.pencolor()
            if winning_color == user_bet:
                print(f"You've won! The {winning_color} turtle is the winner!")
            else:
                print(f"You've lost! The {winning_color} turtle is the winner!")

        rand_distance = random.randint(0, 10)
        turtle.forward(rand_distance)

~The race continues while is_race_on is True.
~Each turtle in all_turtles moves forward by a random distance (between 0 and 10).
~turtle.xcor() > 230: Checks if a turtle has crossed the finish line (x-coordinate greater than 230).
~If a turtle wins, is_race_on is set to False, and the winning color is determined.
~If the winning turtle's color matches the user's bet, a winning message is printed; otherwise, a losing message is printed.

# End of the Program:

screen.exitonclick()

# Conclusion:

This script allows the user to bet on which turtle will win a race. Turtles move randomly towards the finish line, and the script checks the position of each turtle to determine the winner and inform the user if they won or lost their bet. The program utilizes the turtle module for graphical representation and the random module for movement randomness.

# Output1:
![output1](https://github.com/user-attachments/assets/45c66743-7757-4ae1-b488-59393d467186)



# Output2: 
![output2](https://github.com/user-attachments/assets/b7a7a7d5-7aa5-4fa5-8ded-52f57b8ec919)
