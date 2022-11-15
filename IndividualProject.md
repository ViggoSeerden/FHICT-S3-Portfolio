# Individual Project: Tartarus Simulator
### By Viggo Seerden 
Student no. 491216


## Table of Contents

- [Project Description](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#project-description)
- [Technology Stack](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#technology-stack)
- [Documentation](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#documentation)
  - [User Stories](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#user-stories)   
  - [C4 Model](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#c4-model)
-  [UI/UX](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#uiux)
-  [Quality Assurance](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#quality-assurance)
-  [Release Management](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#release-management)
-  [Professionalism](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#professionalism)
-  [Sources](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#sources)
   - [General Sources](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#general-sources)
   - [Game Asset Sources](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#game-asset-sources)

## Project Description
For this project I decided to make a game playable on a website within your browser. 
This game and the website the game is on will communicate with each other and can influence the contents displayed. 
This website has a front end made in the React.JS framework, with a back end written in C#. 
The game is a Unity WebGL project with scripts written in C# and is displayed on the website with the help of the React-Unity-WebGL package for React. 
This package also gives access to the ability to send data both from website to game and vice-versa.

The game is a turn-based RPG dungeon crawler, based on the Shin Megami Tensei/Persona franchises, 
in which you explore randomly generated mazes filled with enemies and treasure. The farther you explore, the tougher the enemies and the better the rewards. 
I chose to make a game of this genre, because it allows for a lot of directions to take with the website. 
For example, normally in a game like this there are shops where you can buy items and equipment for your characters. 
With this website setup, I can handle this in on the website side of things. Certain UI elements could also be displayed on the website instead of in-game, 
so these won’t block your view. There’s a lot of numbers involved for a lot of different types of entities in a game like this, 
so adding a sort of game guide for lost players to the website would be a good idea too. 
I could also allow for players to see other players’ progress, and possibly even create a system where players could interact with each other.

To give each player a way to save their own progression, I’ve made a saving system in Unity that saves a players’ progress to a JSON file. 
The contents of this file can easily be saved to an external SQL database that both the game and the website can access. 
These save files can also be encrypted to prevent anyone from cheating and manually altering the save file.

## Technology Stack
This project (as of now) consists of a React frontend, a .NET backend, and an SQL database. My choices for these options are as follows:

For the frontend, I chose to use React.JS. Personally, I've never worked with a JavaScript-based frontend (or backend, for that matter), 
so I had no experience or knowledge about any possible option. React, along with Vue and Angular, where the example/recommended options listed on Canvas, 
so I decided to choose one of these three. After I thought of the initial idea behind my project, 
I did some research into each of these options and their compatability with Unity WebGL games. I quickly found React-Unity-WebGL, 
a package for React that gave me everything I'd need, with a clear, 
straight to the point documentation that even a newcomer like me could understand on it's installation, uses and functions. Aside from this, 
React was the only one I'd heard of before, and it was often recommended by others, so this choice was easy for me to make.

For the backend, I originally wanted to go with Java. Like with the frontend, I looked at the recommendations on Canvas for this one. 
I'd already used the other recommendation, .NET/C#, in both Semesters 1 and 2 for pretty much everything, so I thought it'd be nice to learn another language.
After a few weeks of developing the game, and doing some research on Java, I changed my mind on this. I had already spent a good amount of time on the game,
so I had some catching up to do for the rest of the project. It's because of this that I ended up going with .NET instead. I was gonna need my time, 
since I didn't just have a website/frontend and API/backend to build from scratch, but also a reasonably big game to make.
My previous experience with .NET would make developing the backend a whole lot quicker, so that's what ended up being used. I should also quickly mention the game. Since it's made in Unity, the scripts are written in C#. This is the standard language Unity uses, so I stuck with it. But this was another reason for me to use .NET for my backend API, since I could use the same save data classes I used in the game without issue. This made some user stories a lot easier to realise, and ended up saving me a lot of time.

## Documentation

### User Stories
Below are the user stories I made. These are for the website, not for the game, since the game isn't a required product for this semester.
First some quick terminology on the customers in the user stories:

- The website visitor is just that: Someone visiting the website who doesn't have an account.
- The website user is someone with an account.
- The player is someone playing the game and using the website features that affect the game.

The user stories are as follows:

- US1: As a website visitor, I want to be able to play the game under any condition, so I don’t need an account to play.
- US2: As a website visitor, I want to be able to make an account so I can save my in-game progress.
- US3: As a website user, I want to be able to change some account details and settings so I can always change them when I need to.
- US4: As a website user, I want to be able to delete my account when I don’t want to play/save anymore.
- US5: As a website visitor, I want to be able to read up on the game’s mechanics, so I don’t get stuck in the game.
- US6: As a website user, I want to be able to manually consent to sharing my profile, so my progress and details can stay private, should I want that.
- US7: As a player, I want to be able to see UI elements with information from the game through the website, so I know how I’m doing in the game.
- US8: As a player, I want to be able to use the currency I collected in the game on the website, so I can buy useful items to use in the game and help me progress.
- US9: As a player, I want to be able to manage my party through the website so I can create the most optimal team in the game which will help with progression.
- US10: As a player, I want to be able to manage and fuse my Demons/Persona’s via the website, so I can increase my strength in the game’s combat situations.
- US11: As a website user, I want to be able to see other players’ progression in the game so I can compare my own progression against others.
- US12: As a website user, I want to be able to interact with other users of the site so I can share communicate with fellow players.
- US13: As a website user, I want to be able to trade Demons/Persona’s with other users to help with progression in the game.
- US14: As a website visitor, I want all pages to load within no longer than 5 seconds so I can efficiently navigate the website.
- US15: As a website visitor, I want the game to load within no longer than 5 seconds after the page has loaded so I can get to playing as soon as possible.
- US16: As a website visitor, I want the site and the game’s written (and spoken?) language to be English so I can understand what’s being shown (or told?) to me.
- US17: As a website user, I want my data and save file to be properly protected so no one can steal my data or tamper with my progress.

To keep track of the progression of the user stories listed above, as well as other tasks, I used a Trello board as seen below:

picture

#### Prioritization
I have prioritized these user stories based on urgency and neccessity using the MoSCoW method:

| Must Have  | Should Have | Could Have | Won't Have |
| ---------- | ----------- | ---------- | ---------- |
| US1        | US5         | US6        |            |
| US2        | US8         | US7        |            |
| US3        | US9         | US11       |            |
| US4        | US10        | US12       |            |
| US16       | US14        | US13       |            |
| US17       |             | US15       |            |

### C4 Model

Below are two parts of a C4 model made for this project, those being the context model and the container model.

picture

## UI/UX

## Quality Assurance

## Release Management

picture

## Professionalism

Throughout the semester, students are expected to show the teachers their work and ask for feedback on what they've made. Students can, of course, also reach out to teachers when a question arises. No matter the outcome or conclusion of one of these conversations, it's important to document them using Feedpulse on Canvas for possible future reference. This process is also one of the eight learning outcomes. I've shown my work on several occasions to the teachers, and have documented these conversations like expected. An example of this can be found here:

picture

More examples can be found on Canvas.

## Sources

### General Sources

Sources used for the creation of the frontend, backend, and game are found here

#### React
- [This video](https://www.youtube.com/watch?v=dGcsHMXbSOA&list=PLDyQo7g0_nsVHmyZZpVJyFn5ojlboVEhE) was used for learning the basics of react
- [This](https://react-unity-webgl.dev/) is React-Unity-WebGL and it's documentation, the React package that allows for Unity WebGL compatability and communication
- Video's 21, 22 and 23 in [this playlist](https://www.youtube.com/playlist?list=PL4cUxeGkcC9gZD-Tvwfod2gaISzfRiP9d) for React routing
- [This bit of code](https://github.com/jeffreylanters/react-unity-webgl/issues/22#issuecomment-1260546499) by a React-Unity-WebGL user for fixing a bug on Unity's end when navigating to other pages on a site hosting a Unity WebGL game 
- [This video](https://www.youtube.com/watch?v=roxC8SMs7HU) and [this video](https://www.youtube.com/watch?v=75aTZq-qoZk&t=826s), both for setting up a Google Authentication system

#### .NET
- [This video](https://www.youtube.com/watch?v=Fbf_ua2t6v4) and [this video](https://www.youtube.com/watch?v=Tj3qsKSNvMk), both for learning how to build a RESTful API

#### Unity
- [This video](https://www.youtube.com/watch?v=aUi9aijvpgs) and [this video](https://www.youtube.com/watch?v=pSY7F6t_7Dw&t=2268s), both for creating a saving and loading system
- [This video](https://www.youtube.com/watch?v=AoD_F1fSFFg&t=499s) for creating an item and inventory system/UI
- [This video](https://www.youtube.com/watch?v=gHU5RQWbmWE) and [this video](https://www.youtube.com/watch?v=gI6G49t--RY&t=857s), both for random dungeon generation
- [This video](https://www.youtube.com/watch?v=28JTTXqMvOU&t=262s) for creating a dynamic minimap
- Video's 1 through 6 in [this playlist](https://www.youtube.com/playlist?list=PLTRrSFerr98V6U-vZeDbA2naLdCbLYnfE), all for creating a turn based combat system
- [This video](https://www.youtube.com/watch?v=r6zhaguEzs8&t=514s) for enemy movement

### Game Asset Sources
Most of the models, textures, and animations, in addition to all music and SFX used in the game were directly ripped from the following games:
-	Persona 3 FES (PlayStation 2)
-	Persona 3 Portable (PlayStation Portable)
-	Persona 4 Golden (Steam/PC)
-	Persona 5 (PlayStation 3)

This was accomplished using the following programs and websites:

- [Amicitia (Site)](https://amicitia.miraheze.org/wiki/Main_Page), for information on file structures, formats, and ripping/conversion tools for the above listed games
- [CriPakGUI](https://shrinefox.com/browse?post=cripakgui), for ripping game assets from Persona 5 and Persona 3 Portable
- [Autodesk 3DS Max](https://www.autodesk.nl/products/3ds-max/overview?term=1-) and [GMD Maxscript Plugin](https://github.com/tge-was-taken/GFD-Studio), for ripping models, textures and animations from Persona 5 and converting them to a usable format
- [Preappfile](https://github.com/tge-was-taken/preappfile), for ripping game files from Persona 4 Golden
- [7zip](https://www.7-zip.org/), for ripping game files from Persona 3 FES
- [Amicitia (Program)](https://github.com/tge-was-taken/Amicitia), for ripping models, textures and animations from Persona 4 Golden, Persona 3 Portable, and Persona 3 FES
- [Noesis](https://richwhitehouse.com/index.php?content=inc_projects.php), for converting models, textures and animations from Persona 4 Golden, Persona 3 Portable and Persona 3 FES to usable formats
- [The Sounds Resource](https://www.sounds-resource.com/), for getting the sound effects used in the above listed games 
- [YouTube](https://www.youtube.com/) and [FLV2MP3](https://www.flv2mp3.by/), for getting the music used in the above listed games
