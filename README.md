# CMSC-202-Project-4-Ben-10-solution

Download Here: [CMSC 202 Project 4 – Ben 10 solution](https://jarviscodinghub.com/assignment/project-4-ben-10-solution/)

For Custom/Original Work email jarviscodinghub@gmail.com/whatsapp +1(541)423-7793

In this project you will:

Practice using C++ class syntax,
Practice implementing member functions,
Implement parent and child classes
Use polymorphism and virtual functions
2.   Background
Ben 10 is a 10-year-old boy named Ben Tennyson who gets a watch-like alien device called the “Omnitrix”. When Ben has the Omnitrix, he can transform into various alien creatures. He then uses these powers to fight evil from earth and space.

This is going to be a round based game where you will be building a catalog of monsters and a variety of alien creatures for Ben to transform into. The game allows Ben to become more powerful as the game continues including the ability to transform into much more powerful creatures.

3.   Assignment Description
This is a traditional Ben10 game where Ben gets to fight with monsters. Because Ben has access to the Omnitrix, Ben can transform into different forms of aliens to help with the battle.

The basic rules of the game are as follows:

This game has between 1 and 20 levels. (user chooses)
Ben can unlock two additional forms for a total of three. (“Normal” Ben, Pyronite, and Crystalsapien)
At the beginning of each level Ben can choose a which form to play with from his available forms.
In this game Ben and the monster have their own life. Ben starts at 100. The monster’s life is calculated for each level. The monsters gain power as Ben goes up in level.
If Ben reaches 0 life, he is defeated and loses the game. If a monster is defeated, Ben progresses to the next level unless it is the last level at which point, Ben wins.
At level 1, Ben only has access to Ben. At level 2, Ben has access to Ben and Pyronite. At level 3 and above, Ben has access to Ben, Pyronite, and Crystalsapien.
The attack will always alternate between Ben (or a form of Ben) and the monster. Ben always gets to attack first each round.
Every form of Ben has a normal attack and a special attack. You can use an unlimited number of normal attacks. Normal attacks are a range (1-10 for example) and are based on the specific form of Ben.
It is possible for normal attacks to miss.
The special attacks have a finite number usually one or two before they are exhausted. They always hit for the same amount. Special attacks never refill between levels.
Special attacks never miss.
The Crystalsapien form of Ben also has an Ultimate Attack that is unlimited.
Ultimate attacks never miss and do 10x the special attack.
Monsters (villains) are random and are chosen from a file (monster.txt) of 29 options.
Monsters do the same damage throughout the level. As the level progresses, they do more damage.
This is the table of stats for each of the forms of Ben.

 

This is the table of damage for the monsters by round:

 

4.   Requirements:
Initially, you will have to use the following files Ben.h, Crystalsapien.h, Pyronite.h, Monster.h, Game.h, makefile, monster.txt and proj4.cpp. You can copy the files from Prof. Dixon’s folder at:

/afs/umbc.edu/users/j/d/jdixon/pub/cs202/proj4

To copy it into your project folder, just navigate to your project 4 folder in your home folder and use the command:

cp /afs/umbc.edu/users/j/d/jdixon/pub/cs202/proj4/*.* .

Notice the trailing period is required (it says copy it into this folder).

The project must be completed in C++. You may not use any libraries or data structures that we have not learned in class. Libraries we have learned include <iostream>, <fstream>, <iomanip>, <vector>, <stdlib.h>, <time.h>, <cmath>, <limits>, and <string>. You should only use namespace std.
You must use the function prototypes as outlined in the each of the header files. Do not edit any of the .h files except to add friend functions (not necessary though).
All user input should be validated at least for described ranges. You can assume that the user will enter the correct type of data.
Next you need to code up the various functions that are called in the corresponding .cpp file that are prototyped in the .h
class Monster – Manages all of the baddies in this game. Monsters are pretty simple, no inheritance. Just imports file into a vector and then generates a list of monsters to fight for each level.
class Ben – Parent class of all good guys in this game. It has several data members that are populated during the constructor. Has some virtual functions that are overridden by child classes including Pyronite and Crystalsapien.
Class Pyronite – Child class of Ben. Inherits lots of stuff and overrides Attack and Special Attack. Does not have an Ultimate Attack.
class crystalsapien – Child class of Ben. Inherits lots of stuff and overrides Attack and Special Attack. Includes a special Ultimate Attack.
class game – This is the class that controls the entire game. It initializes the Monsters, and Ben. It also identifies how many rounds (up to 20) the user would like to play. Deals with win/loss scenarios, battle, and the menu. Has an important destructor to make sure that there are no memory leaks!
5.   Sample Input and Output
5.1.                Sample Run
A normal run of the compiled code would look like this with user input highlighted in blue:

-bash-4.1$ ./proj4
How many levels would you like to try?

3

The game starts….

LEVEL 1 of 3

Select one from the available forms of Ben at level 1 are:

1.Ben

What would you like to do?

Enter 1 to 1:

1

BEN: Ben

MONSTER: Howell Waynewright

The start life of Ben is: 100

The start life of Howell Waynewright is: 76

Ben: 100     Howell Waynewright: 76

What would you like to do?

1. Normal Attack

2. Special AttackNon

3. Ultimate Attack

Enter 1 to 3:

3

Ben has no ultimate attack! Howell Waynewright retaliates!

Howell Waynewright attacks Ben using a normal attack.

Howell Waynewright did 11 to Ben.

Ben: 89     Howell Waynewright: 76

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

2

Ben attacks using his kick attack.

Ben did 25 to Howell Waynewright.

Howell Waynewright attacks Ben using a normal attack.

Howell Waynewright did 11 to Ben.

Ben: 78     Howell Waynewright: 51

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

2

Ben attacks using his kick attack.

Ben did 25 to Howell Waynewright.

Howell Waynewright attacks Ben using a normal attack.

Howell Waynewright did 11 to Ben.

Ben: 67     Howell Waynewright: 26

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

2

Ben is out of special attacks! Howell Waynewright retaliates!

Howell Waynewright attacks Ben using a normal attack.

Howell Waynewright did 11 to Ben.

Ben: 56     Howell Waynewright: 26

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

1

Ben attacks using his hand-to-hand attack.

Ben did 19 to Howell Waynewright.

Howell Waynewright attacks Ben using a normal attack.

Howell Waynewright did 11 to Ben.

Ben: 45     Howell Waynewright: 7

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

1

Ben attacks using his hand-to-hand attack.

Ben did 19 to Howell Waynewright.

Congrats! Ben won that level.

The game starts….

LEVEL 2 of 3

Select one from the available forms of Ben at level 2 are:

1.Ben

2.Pyronite

What would you like to do?

Enter 1 to 2:

Level 2 might look like this:

2
BEN: Pyronite

MONSTER: The Alien Mummy

The start life of Pyronite is: 45

The start life of The Alien Mummy is: 43

Pyronite: 45     The Alien Mummy: 43

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

2

Pyronite attacks using his flamer attack.

Pyronite did 30 to The Alien Mummy.

The Alien Mummy attacks Pyronite using a normal attack.

The Alien Mummy did 5 to Pyronite.

Pyronite: 40     The Alien Mummy: 13

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

1

Pyronite attacks using his flame attack.

Pyronite did 21 to The Alien Mummy.

Congrats! Pyronite won that level.

The game starts….

LEVEL 3 of 3

Select one from the available forms of Ben at level 3 are:

1.Ben

2.Pyronite

3.Crystalsapien

What would you like to do?

Enter 1 to 3:

Finally, round 3 might look like this:

3
3

BEN: Crystalsapien

MONSTER: Coach Finn

The start life of Crystalsapien is: 40

The start life of Coach Finn is: 89

Crystalsapien: 40     Coach Finn: 89

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

3

Crystalsapien attacks using **ULTIMATE** ATTACK!!

Crystalsapien did 100 to Coach Finn.

Congrats! Crystalsapien won that level.

Congrats! You won the game.

-bash-4.1$

Some additional validation would look like this:

-bash-4.1$ ./proj4
How many levels would you like to try?

31

You should do less than 20 levels!

How many levels would you like to try?

3

The game starts….

LEVEL 1 of 3

Select one from the available forms of Ben at level 1 are:

1.Ben

What would you like to do?

Enter 1 to 1:

4

Invalid input; please re-enter.

What would you like to do?

Enter 1 to 1:

0

Invalid input; please re-enter.

What would you like to do?

Enter 1 to 1:

And once the battle begins.

BEN: Ben
MONSTER: Phil

The start life of Ben is: 100

The start life of Phil is: 101

Ben: 100     Phil: 101

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

4

Invalid input; please re-enter.

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

0

Invalid input; please re-enter.

What would you like to do?

1. Normal Attack

2. Special Attack

3. Ultimate Attack

Enter 1 to 3:

6.   Compiling and Running
Because we are using a significant amount of dynamic memory for this project, you are required to manage any memory leaks that might be created. For this project, make sure that your game class has a good destructor. The game destructor should be deallocating any dynamic memory that was used.

One way to test to make sure that you have successfully removed any of the memory leaks is to use the valgrind command.

Since this project makes extensive use of dynamic memory, it is important that you test your program for memory leaks using valgrind:

valgrind ./proj4

If you have no memory leaks, you should see output like the following:

==14746==

==14746== HEAP SUMMARY:

==14746==     in use at exit: 0 bytes in 0 blocks

==14746==   total heap usage: 42 allocs, 42 frees, 931 bytes allocated

==14746==

==14746== All heap blocks were freed — no leaks are possible

==14746==

==14746== For counts of detected and suppressed errors, rerun with: -v

==14746== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 6 from 6)

The important part is “in use at exit: 0 bytes 0 blocks,” which tells me all the dynamic memory was deleted before the program exited. If you see anything other than “0 bytes 0 blocks” there is probably an error in one of your destructors. We will evaluate this as part of the grading for this project.

Additional information on valgrind can be found here: https://valgrind.org/docs/manual/quick-start.html

Based on our practice this semester, you need to write your own makefile to compile and run your code. Your final output file should be proj4.

7.   Completing your Project
When you have completed your project, you can copy it into the submission folder. You can copy your files into the submission folder as many times as you like (before the due date). We will only grade what is in your submission folder.

For this project, you should submit these files to the proj4 subdirectory:

Monster.cpp – should include your implementations of the class functions

Ben.cpp – should include your implementations of the class functions

Pyronite.cpp – should include your implementations of the class functions

Crystalsapien.cpp – should include your implementations of the class functions

Game.cpp – should include your implementations of the class functions

None of the original header files should be changed (.h).

As you should have already set up your symbolic link for this class, you can just copy your files listed above to the submission folder

cd to your project 4 folder. An example might be cd ~/202/projects/proj4
cp Monster.cpp Ben.cpp Pyronite.cpp Crystalsapien.cpp Game.cpp LinkedList.cpp ~/cs202proj/proj4
You can check to make sure that your files were successfully copied over to the submission directory by entering the command

ls ~/cs202proj/proj4

You can check that your program compiles and runs in the proj4 directory, but please clean up any .o and executable files. Again, do not develop your code in this directory and you should not have the only copy of your program here.

For additional information about project submissions, there is a more complete document available in Blackboard under “Course Materials” and “Project Submission.”

IMPORTANT: If you want to submit the project late (after the due date), you will need to copy your files to the appropriate late folder. If you can no longer copy the files into the proj4 folder, it is because the due date has passed. You should be able to see your proj4 files but you can no longer edit or copy the files in to your proj4 folder. (They will be read only)

If it is 0-24 hours late, copy your files to ~/cs202proj/proj4-late1
If it is 24-48 hours late, copy your files to ~/cs202proj/proj4-late2
If it is after 48 hours late, it is too late to be submitted.

