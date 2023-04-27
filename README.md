﻿<p align="center">
  <a href="https://play.plasma.games" target="blank"><img src="https://dkmzd4tgwtjws.cloudfront.net/public/images/logos/plasma_logo_h.png" width="320" alt="Nest Logo" /></a>
</p>

# 🎮 Unity Interview Task
![](./Assets/Included/Wires.gif)
I started off with art assets, I found a serviceable still-image from the provided gif, and began cutting it up into relevant pieces. I was going to use the wires but my lack of art formatting knowledge was causing some strange issues. I ended up finding a free little wire pack with white wires which was more desirable, as now the wires can be colored however we like through Unity. I used one script for the wires, using a collider on the wire sockets on the other side that I would call when the wire was plugged into a socket. There is one smaller wire script that randomizes children, attached to the socket side and wire side to randomize them each time. The wire script allows us to plug in the wire to a socket, which will then call to the socket to play it's particle system, and we also call to the main camera that has our sound listener and sound to play upon connecting a wire. We take the question text directly from the text that is displayed to the user, and then run a comparison against the answer attached to the wire through the QAHandler.
We run the comparison in QAHandler by passing both strings into a dictionary beforehand, and then running a check on the 'key' in the 'key value pair' which runs more efficiently than if we were to check string to string through the entire JSON file, so this approach has scalability in mind. We start off in QAHandler also by getting the amount of QA sets, so that we know how many sets need to be answered before we go to the scoring scene. Like mentioned in the comments in the code, if say 8 questions were given, I would simply need to specify in the script that every 4 questions we would reload with 4 new questions, and still check until we have the total amount of QA sets answered before scoring, so this setup can easily take on new questions and is only currently limited by the layout of the UI allowing for sets of 4 questions at a time. One other gripe in the comments is that I have set up QAHandler.cs in a way that is focused more on solving wire problems, if another game were needed in addition to the wires I would likely break up the script to allow it to handle different game types, with scripts that inherit from it that more specifically calculate scores for different kinds of games as needed. If I worked on this project further, I would add more null checks for some of the objects. They all work because all of the components are attached, although Unity would quickly let us know if during play a object did not have the expected component I would begin adding more null checks and also require components. Using
the require component functionality in a script will make the script complain and stop play if the object it is attached to is not provided with the required components. Things like this can help a more complex, growing system from failing due to developer error. I used prefabs lightly in this project, but they are usually integral to the process. I changed a few values quickly on the wires by going through each of the four, but if there were 20, that is where keeping one wire prefab updated would come in handy and be quite necessary to the process.
## 📝 Task Description

In this task, you will be asked to develop a simple 2D game using Unity. Your task is to build a "Wire Matching" game 
like the example
below. 

![](./Assets/Included/wire-matching.gif)

The game you create should try to match the style and format of the example. For the game we will provide you with the 
list of matching questions. These will be given in a JSON format and can be found in the `Assests/Included` folder. You should use the JSON as a template for your own C# class or struct that includes the same fields and any relevant functionality you think the class should have. 

Even though your game will only have this one set of questions, the Wire Matching module you create should be able to take in any set of questions that follows the C# class or struct you define. Meaning the questions should not be hard coded in the Wire Matching module, but should be passed into the module as an instance of your class or struct. The goal is to allow question sets to be switched out quickly and easily. Like any good matching quiz, the display order of the question and answers should be randomly ordered. 


The game should have the following features:
- Ability to drag and drop "wires" to match questions to answers. 
- System or Script that marks answered questions as correct or incorrect.
- Ability to randomize the positioning of the questions and answers on the Wire Matching Module.
- Provide a grade report that presents the final grade of the activity.

## 📋 Requirements

- You may use any free art or design assets from the Unity Asset Store.
- You may NOT use any scripts from the Unity Asset Store. All code must be your own.
- You should use C# as the scripting language.
- You should use Git for version control and commit your work frequently.
- You should provide a brief write-up explaining the thought process behind your implementation.
- The game must include at least 2 scenes.
- The game must include a drag and drop mechanic for dragging and dropping the wires.
- The game must include a Unity animation.
- The game must be scalable to the most common aspect ratios.
- The game must be playable as a WebGL build

## 🛠️ How to Get Started

1. Click the "Fork" button on the top right corner of the GitHub repository page.
2. Select the account or organization to which you want to fork the repository.
3. Wait for the forking process to complete.
4. Clone the forked repository to your local machine.
5. Open the project in Unity 2020.3.47f1
6. Start working 🙂
7. Send the link of the forked repository to [Zach Haymore](mailto:zach@plasma.games) at `zach@plasma.games`.

If you have any questions, please contact [Zach Haymore](mailto:zach@plasma.games) at `zach@plasma.games`.

## 📂 Included Code

In the `Assets/Included` folder, you will find the JSON of the matching questions you should use in the game.

## 📤 Submission

Please upload and push your commits to your forked, public GitHub repository and send the link to [Zach Haymore](mailto:zach@plasma.games) 
at `zach@plasma.games`. Please make sure to include a README file that explains how to run the game and any other 
relevant information about the project.

Good luck and have fun! 🚀


