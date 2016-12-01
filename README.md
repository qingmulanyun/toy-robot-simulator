# toy-robot-simulator

Implementation for toy robot test by ruby. \n
Test with rspec.



Overveiw
  I think there are 4 main objects to solve this problem.
   robot: A class storing current positon info of itself.
   table: A class storing the table info. (5X5 units) 
   command: The object to handle user input or file via (ARGF)
   simulator: The object that really do the movement for robot.
   
  Start a new client, recieving user input and translate these input into command which simulator could understand and the simulator will reset the new (X,Y) or facing for the robot according to the command.


  The most interesting part of this development is finding a way to extract the reallife problem into a data structure. We need translate user input into the robot position info. So from a high level, what we need to do is a info translation.
  For this test,I use an array to store 4 directions(N,E,S,W). In order to implement the left and right action, just +1 or -1 on the index of the robot current direction.
  It is a 5X5 units table. So we can use the concept of axis. 
  Here is the mapping between move action and axis:
  Move North => y + 1
  Move East => x + 1
  Move South => y - 1
  Move West => x - 1

  After the actions are completed, we print current position info of the robot.
  
Usage
  Start: 1. bundle install 
         2.bin/toy-robot
  test: rspec spec
  
  
What need to improve
  I did not have much time on this test, so I completed it in a hurry. Some error exception rescue and logger should be added. So that when user input an invalid command they can get more understandable error msg and the developer could take advantage of the log file to debug. 
