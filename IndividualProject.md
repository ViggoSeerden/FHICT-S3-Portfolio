# Individual Project: Tartarus Simulator
### By Viggo Seerden 
Student no. 491216

![tartarussimlogo](https://user-images.githubusercontent.com/100349697/203649141-82c8d347-ebd5-444a-acef-820b5f7d6168.png)

## Table of Contents

- [Project Description](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#project-description)
  - [Technology Stack](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#technology-stack)
    - [Front-End](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#front-end)
    - [Back-End](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#back-end)
    - [Database & Persistence](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#database--persistence) 
- [Documentation](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#documentation)
  - [User Stories](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#user-stories)
    - [Prioritisation](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#prioritisation)    
  - [C4 Model](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#c4-model)
- [UI/UX](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#uiux)
  - [UI](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#ui)
  - [UX](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#ux)
- [Quality Assurance](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#quality-assurance)
  - [Testing](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#testing)
    - [Unit Tests](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#unit-tests)
    - [Integration Tests](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#integration-tests)
    - [Usability Tests](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#usability-tests)
  - [Code Analysis](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#code-analysis)   
  - [Performance](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#performance)
  - [Security](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#security)  
- [Release Management](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#release-management)
  - [Version Control](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#version-control)
  - [CI/CD](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#cicd)
- [Business Process](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#business-process)
- [Professionalism](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#professionalism)
  - [Feedback](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#feedback)
  - [Reflection](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#reflection)   
- [Sources](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#sources)

## Project Description
For this project I decided to make a game playable on a website within your browser. 
This game and the website the game will communicate with each other and can influence the contents displayed. 
This website has a front end made in the React.JS framework, with a back end written in C#. 
The game is a Unity WebGL project with scripts written in C# and is displayed on the website with the help of the React-Unity-WebGL package for React. 
This package also gives access to the ability to send data both from website to game and vice-versa.

The game is a turn-based RPG dungeon crawler, based on the Shin Megami Tensei/Persona franchises, specifically Persona 3. This game, and by extension, the rest of the franchise, was fresh on my mind since I had  played through the entire 80-ish hour experience over the course of a year and thoroughly enjoyed it, with me finishing it right before the end of summer break. In the game, you explore randomly generated mazes filled with enemies and treasure. The farther you explore, the tougher the enemies and the better the rewards. A game of this genre would be a good fit for a website setup too, because it allows for a lot of directions to take with the website. For example, normally in a game like this there are shops where you can buy items and equipment for your characters. With this website setup, I can handle this in on the website side of things. Certain UI elements could also be displayed on the website instead of in-game, so these won’t block your view. There’s a lot of numbers involved for a lot of different types of entities in a game like this, so adding a sort of game guide for lost players to the website would be a good idea too. I could also allow for players to see other players’ progress, and possibly even create a system where players could interact with each other.

To give each player a way to save their own progression, I made a saving system in Unity that saves a players’ progress to a JSON file. 
The contents of this file can easily be saved to an external SQL database that both the game and the website can access. 
These save files can also be encrypted to prevent anyone from cheating and manually altering the save file.

### Technology Stack
This project (as of now) consists of two React front-ends, one of which is an admin front-end, a .NET back-end, and an SQL database. My choices for these options are as follows:

#### Front-End

For the front-end, I chose to use React.JS. Personally, I've never worked with a JavaScript-based front-end (or back-end, for that matter), 
so I had no experience or knowledge about any possible option. React, along with Vue and Angular, where the example/recommended options listed on Canvas, 
so I decided to choose one of these three. After I thought of the initial idea behind my project, 
I did some research into each of these options and their compatability with Unity WebGL games. I quickly found React-Unity-WebGL, 
a package for React that gave me everything I'd need, with a clear, 
straight to the point documentation that even a newcomer like me could understand on it's installation, uses and functions. Aside from this, 
React was the only one I'd heard of before, and it was often recommended by others, so this choice was easy for me to make.

Below is a picture of the front-end/website:

<img width="941" alt="site" src="https://user-images.githubusercontent.com/100349697/203651773-c6737cf1-4e6f-4d63-98b4-6f2b70313b26.png">

#### Back-End

For the back-end, I originally wanted to go with Java. Like with the front-end, I looked at the recommendations on Canvas for this one. 
I'd already used the other recommendation, .NET/C#, in both Semesters 1 and 2 for pretty much everything, so I thought it'd be nice to learn another language.
After a few weeks of developing the game, and doing some research on Java, I changed my mind on this. I had already spent a good amount of time on the game,
so I had some catching up to do for the rest of the project. It's because of this that I ended up going with .NET instead. I was gonna need my time, 
since I didn't just have a website/front-end and API/back-end to build from scratch, but also a reasonably big game to make.
My previous experience with .NET would make developing the back-end a whole lot quicker, so that's what ended up being used. I should also quickly mention the game. Since it's made in Unity, the scripts are written in C#. This is the standard language Unity uses, so I stuck with it. But this was another reason for me to use .NET for my back-end API, since I could use the same save data classes and even some logic that I used in the game without issue. This made some user stories a lot easier to realise, and ended up saving me a lot of time.

Below is a picture of the API's Swagger page:

<img width="941" alt="swagger" src="https://user-images.githubusercontent.com/100349697/203651788-a0f4b355-36d3-4c54-bb5c-404de9b91760.png">

#### Database & Persistence

Finally, this back-end is connected to an SQL database. I chose to use an SQL-based database as opposed to a NoSQL one, again, due to experience and it saving time. I do have to admit, though, that a NoSQL database actually might have been the better choice, due to my current database not having any relations between tables, and because I save JSON savefiles in my database. 

I access and alter the data in there using an ORM in my back-end. An ORM is a technique used to establish a connection between a relational database and an object oriented programming language. This pretty much means the conversion of a OOP object to database-compatible data to be stored after a system or program is shut down, and vice-versa, also known as data persistance. My choice ended up being Entity Framework. This is, once more, due to past expecience with it from my group project in semester 2, and also due to a good amount of recommendations online after some quick research for .NET ORMs. The other most popular option that I came accross while searching for recommendations from fellow programmers (aside from writing pure SQL) is Dapper, which is classified as a micro ORM (which only does the O and M in ORM). The most prominent reason as to why someone would choose Dapper over other ORMs is performance. However I found EF to perform just fine, so I don't feel to switch ORMs. Micro ORMs also lack features that I needed such as database migrations, which I used to generate tables using my domain models and migrations.  

## Documentation

Keeping documentation of my application helps me stay organised during development, and is important for any outsiders to get an idea of how everything was put together. 

### User Stories
Below are the user stories I made. These are for the website, not for the game, since the game isn't a required product for this semester. I chose to write user stories instead of requirements due to them being more flexible compared to requirements.
First some quick terminology on the people mentioned in the user stories:

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

<img width="853" alt="trello" src="https://user-images.githubusercontent.com/100349697/203642404-81dc53ed-580b-4d45-9bdf-01a470eec58c.png">

Sadly, I wasn't able to actually implement as many user stories as I'd hoped due to time constraints, but at least the core is there.

#### Prioritisation
I have prioritized these user stories based on urgency and neccessity using the MoSCoW method:

| Must Have  | Should Have | Could Have | Won't Have |
| ---------- | ----------- | ---------- | ---------- |
| US1        | US5         | US3        | US7        |
| US2        | US8         | US6        | US13       |
| US4        | US9         | US11       |            |
| US16       | US10        | US12       |            |
| US17       | US14        | US15       |            |

### C4 Model

Below are two parts of a C4 model made for this project, those being the context model and the container model.

Context:

![context](https://user-images.githubusercontent.com/100349697/203642356-7dcecb9f-1935-400d-9a5c-259a307baa73.png)

Container:

![container](https://user-images.githubusercontent.com/100349697/203642380-8b2937ee-4890-4935-9f4a-c00d620a7dc5.png)

## UI/UX

Making my website look appealing to potential users, while also keeping the experience nice. Below, you'll find what I've done to achieve this, explained in detail.

### UI

Since I based my website and game on an existing piece of media, specifically the game Persona 3, I tried to apply a similar style to my website. The Persona series is well known for it's art styles. Every game in the series has one color that's used throughout the entire game for it's UI. In Persona 3's case, that's blue, however in some parts of the game, specifically the parts that inspired my project, it's green, so that's the color I mainly used, with hints of blue here and there. For context, the blue is used in the non-dungeon crawling parts of the game, which aren't in my game at all, however, that's not to say that the blue doesn't appear in these parts of the game. First of all, I created a logo using elements from Persona 3:

![tartarussimlogo](https://user-images.githubusercontent.com/100349697/203649141-82c8d347-ebd5-444a-acef-820b5f7d6168.png)

I won't go into too much detail about the Persona 3 stuff, since I'd have to write a whole plot synopsis of the entire 80-hour game, but I'll try to give a simple explanation here. Persona 3's story is about a phenomenon known as the Dark Hour. It's during this hour that the tower seen behind the green cloud appears. This tower, known as Tartarus, is where the game on my website takes place, except in my game, it's supposed to be a simulation, not the real thing. During the Dark Hour, a greenish fog appears across the terrain, so hence the green cloud. The moon also gets a green tint, so thats represented here too. The blue clock overlapping the moon is taken straight from Persona 3, since this clock appears right before the Dark Hour starts, as the clock strikes midnight. Finally, if you look closely, you'll see binary code in the moon, to represent the fact that my game is supposed to be a mere simulation of the Dark Hour. Finally, the font used for the logo's text is the same font that's used for Persona 3's logo, except with it's color inverted and a black glow to make it more easily readable and stand out from the (admittedly kind of busy) background.

On the website, the background is an image of Tartarus, with a looping subtle green fog overlapping it. Like in Persona 3, the text is mainly white. I did make some containers for text, as seen under the news section, which have a very slight bluish tint and glow to them:

<img width="1201" alt="Screenshot 2022-12-01 105732" src="https://user-images.githubusercontent.com/100349697/205023392-597800a2-eef6-4f90-a0b2-dcb37e3ce01e.png">

### UX

I implemented some basic features and quality-of-life features into the website. The main thing related to this is the navigation bar at the top of the page. This was made with the Canvas course on user experience. This meant designing the navigation system while keeping the following questions in mind:

- Where am I
- How did I get here?
- What can I do here?
- Where can I go from here?

My site isn't that much of a maze of pages, thankfully. This means that there aren't many pages only accessible through other specific pages. In fact, there would've  only been two pages for which this is the case; the player profiles and trading screen. These generally aren't pages you'd need to access frequently though, so it's all good, and in the case of player profiles, there's a whole pages dedicated to accessing those under the Players tab on the navbar. I kept the page names as simple and clear as possible. While I could've been more creative with some of them (I was originally planning to name the Players page "Player Hub"), keeping things straightforward reduces the chance of raising any questions among potential visitors. Aside from that, there are a few pages related to your own account hidden in a sub-menu, which is shown when hovering over your username in the navbar while logged in:

![Screenshot (6)](https://user-images.githubusercontent.com/100349697/205982799-d21e104d-7f22-44e2-b9eb-578ade46241a.png)

These all belong to the same category, so keeping them together seemed like a good idea. Not to mention the fact that many other sites and apps do the same practice of categorising pages under sub-menus, most commonly for things relating to user accounts like what I did here. It also makes the navbar feel less cluttured and cramped, in my opinion at least.

Navigation isn't the only part of UX, though. Canvas mentions *adjusting the design to suit your end-users* and *designing a corporate identity for the webpage in accordance with your client*. There's no real client in the individual project, but I can design my website to appeal to my end-users. I've already explained my mindset when designing the UI for the general front-end above, so there's no need to go over it again. My admin front-end, however, lacks any style to be spoken of:

<img width="640" alt="admin" src="https://user-images.githubusercontent.com/100349697/205984324-a3bda83e-9dca-43a3-b967-188ccc946a20.png">

An admin front-end doesn't really need any style, though. Keeping things "professional" is probably more suitable for content management. Packing this site with fun colors and shapes can be very distracting. Now obviously what I have here may be a bit too minimalistic, but I don't feel any need to make things much more complex than this, with the time I have for this project. The same navigation philosophy applies to the admin front-end, though. Quick navigation may very well improve productivity for content management, after all. 

Aside from everything mentioned above, I performed some usability tests. More on these can be found under the corresponding heading.

## Quality Assurance

Ensuring the quality of software is an important task. Creating an application held together by ducktape isn't only a hinderance to users, but also to developers. To circumvent this, there are several measures you can take. I have chosen to perform several types of tests, use a static code analysis tool, pay mind to performance using scanning tools, and implement some features for securities' sake, to create an application of quality.

### Testing

My testplan is quite simple. I plan to create unit- and integration tests for my back-end, for testing logic and connections. This will be done using MSTest projects. I chose to use MSTest over something like xUnit because I personally find MSTest to be a bit more clear with it's keywords, with test methods actually being called *TestMethod* instead of something kind of vague like *Fact*. The logic tested is the save file editing I do in my back-end, which requires the serialising and deserialising of the JSON save files. Thankfully since the game was written in C#, I can use the exact same classes for serialisation. Integration tests will be done on my controllers, by using "fake" HTTP client to make requests to the controllers. I will make calls to these controllers which should then return data from an in-memory database.

As for the front-end, aside from Google Lighthouse scans every so often, I plan on doing usability tests to make sure my site is easily navigatable. These usability tests will be done by asking fellow students and a few friends (some of which are also knowledgeable on web development, and some are not) to do simple tasks on the site, like registering an account and playing the game. Aside from playing the game, there aren't many other features to utelise, so I plan on asking them to navigate to other pages and change game settings like audio volume and screen size. Aside from that, I'll ask them about the website's style. All this is to gather feedback for potential improvement.

Aside from this, I will keep track of the performance of my websites using Google Lighthouse, and get my code analysed using SonarCloud. I can get an idea of what needs to be improved or changed in my front-end and back-end respectively. Google Lighthouse can give me an idea of what performance gains can be made, no matter how big or small, while also giving some insights on some small user experience improvements that could be made. SonarCloud can not only tell me what parts of my code could be optimised, but it can also detect bugs, security risks, and duplications, alongside tracking test code coverage using an extra package for .NET.

#### Unit Tests

The unit tests test the save data alteration I do in my back-end's service classes, which is pure logic. An example can be found below:

<img width="564" alt="unit test" src="https://user-images.githubusercontent.com/100349697/203649883-61447b46-c04d-4d5f-89c3-50d1b0d439fd.png">

In this test, I simulate buying an item, and thus testing the logic behind adding this item to the save file, while also making sure to subtract the correct price from the users balance. This is all checked at the end. 

#### Integration Tests

My integration tests test the connection to the back-end, and by extension the database. An example can be found below:

<img width="651" alt="integration test" src="https://user-images.githubusercontent.com/100349697/203650269-db2ff834-3632-4a38-9b86-6220f791e3a0.png">

In this test, I simulate the process of adding a new user to the database. This is possible thanks to a NuGet package called *Microsoft.AspNetCore.Mvc.Testing*, which allows me to emulate an HTTP request, which can then access the correct function in my controller, which executes the code like normal. I then check the response by first converting it to a more readable string format, and then checking if it contains the correct data. I also check for the correct status code. It should be noted that the database used for this is an in-memory one, which means the data used for this is not the actual database used for my website. I achieved this by overriding my *Program.cs* file (which is where the database to use is set through a connection string) in a seperate class in my test project:

<img width="389" alt="inmemory" src="https://user-images.githubusercontent.com/100349697/205496620-834ffbdf-2a47-4ac6-a7c6-9e2ca6702fdf.png">

This function is called in the test class' constructor, so the *client* being called in the example test method above (at *client.PostAsync*) is using the in-memory database. Like I said, this in-memory database is instantiated in the constructor, where it's also filled with some data for testing *GET*, *PUT* and *DELETE* calls:

<img width="520" alt="constructor" src="https://user-images.githubusercontent.com/100349697/205496827-57cc1a47-1813-41b2-b093-4025b93ace9b.png">

#### Usability Tests

WIP

### Code Analysis

I used SonarCloud to review my back-end project. This program checks for any bugs, unneccessary code, unoptimal code, and security risks, and gives advice and explanations about why a part of my code is classified as such, should it detect any of the above mentioned issues. My code passed every section with an A, and the quality gate is marked as passed. However, SonarCloud doesn't natively support tested code coverage for .NET projects, so I had to use an external dotnet package which allows for SonarCloud to display this too. There were a few options listed on SonarCloud's own site, and I went with the package *dotnet-coverage*, since it's a more modern and more accessible version of an official Microsoft option which was also listed.

<img width="823" alt="sonar" src="https://user-images.githubusercontent.com/100349697/205058215-83e64fb2-c476-4922-98f5-7e5f8f51f27b.png">

(This screenshot was taken when I didn't have a lot of tests yet, so the coverage percentage shown here is higher in actuality.)

### Performance

I have been continuously monitoring my websites performance using Google Lighthouse as seen below:

<img width="301" alt="lighthouse" src="https://user-images.githubusercontent.com/100349697/203652520-90346590-e417-43cd-9b02-e40b8e42c15c.png">

Every so often, usually after adding features or style changes, I run a Lighthouse scan like this to find any possible bottlenecks affecting performance. I want to keep this score at 90 or higher for optimal performance. An example of a change I made is that the performance score used to be much lower, due to me using a less optimal image file (.png instead of .webp) for the logo on the main page, which had such a heavy impact on the performance that the score dropped all the way to a 6.3. After fixing this, however, there remain few optimisations to be made, none of which give any notable performance gains.

### Security

My website relies on accounts to work properly, since I want every user to have their onw save file for the game. This means my website needed some form of authentication. I decided to use Sign in with Google for this. Being able to create accounts using Google means that pretty much most people nowadays can easily create an account due to Google's popularity. The Sign in with Google feature itself is also incredibly popular, which meant proper documentation was easily accessible. But I also chose this for security reasons. There's simply no way I can create a more secure login system by myself with my current knowledge and time constraints. Google is also a trusted name worldwide. There are a few downsides to this, though. First of all, any potential users would have to trust me not to misuse their data, which is easier said than done, however, since I have no plans of publicly launching this website, that's not a concern. But aside from that, I have to rely on Google to keep my system working as expected. If Google were to go down, even just temporarily, my webiste would lose over half of it's functionality. I'm not worried about this, since I doubt something as big as Google's servers and databases and whatnot would go down so easily, but it is a risk nonetheless. There's also the risk of Google deciding the Sign in with Google feature is no longer needed and pulling support for whatever reason, and them either creating a new system entirely, or not making one anymore at all. Replacing an existing system with a new one has already happened fairly recently with OAuth 2.0, whose days of support are numbered. But the chances of this happening anytime soon are incredibly low, so i'm not worried about that either. As you can see, to me, the good easily outweighs the bad, so I think Sign in with Google was a good option to go with.

Aside from this, I have implemented a security measure within the Unity project, which gives me the option to encrypt save files before saving them. This is done using *X-OR encryption*. Data protection was one of the topics for my research reports, and encryption is one way to protect data. It should be mentioned that, throughout this project, this option has been turned off for debugging purposes.

Finally, using SonarCloud, I can see any possible security risks that appear in my code. Some of these are classified as vunerabilities immediatly, while others are put aside for me to review manually. Thankfully, despite the usefull feature, I haven't run into any major risks yet. Only a few minor things for me to review, which all turned out to be fine.

## Release Management

### Version Control

I have been using GitHub repositories as my version control system of choice, one each for both front-ends and the back-end. Below is an example of one of my GitHub repositories:

<img width="792" alt="github frontend" src="https://user-images.githubusercontent.com/100349697/203647973-12b4aa5d-4b2a-4f13-9ec2-b84d49cd229f.png">

I chose to use GitHub due to my previous experience in using it during last semesters' group project, and due to it's popularity. As for branching, at the time of writing this, every repository has two branches: main (or master), and develop. The develop branch is for developing new features. This is done so that, in the case that something goes wrong, I always have a stable version to go back to on the main. The main branch only gets pushed to once I'm sure any changes I made work as intended on the develop branch. Once something gets pushed to the main, the CI/CD gets activated. More on that below.

### CI/CD

To automate certain aspects of my application, namely building, testing, and code reviewing, alongside deploying my application to DockerHub, I have created a CI/CD pipeline using GitHub Actions for every repository, which was configured with Configuration as Code. CI/CD stands for continuous integration and continuous delivery and/or continuous deployment. In our case, only continuous integration and delivery were required by the learning outcomes. Continuous deployment means automatically deploying your software to production, which I can't do, due to there being no production to speak of. I'll be using CD to refer to continuous delivery from here on out. The CI part is used for building and testing your application, while the CD part is used for uploading your project to a repository or container registry. In my case, I also used the CI to upload my project to SonarCloud, a static code analysis tool, since the building and testing commands are used during this process. I mentioned that I use DockerHub in the CD part of my pipeline, which means I containerize my app. This means bundling all code and packages together to an easily portable and lightweight container image. 

Below is an example of the back-end pipeline:

```
name: CI/CD

on:
  push:
    branches: [ "master" ]
  pull_request:
    branches: [ "master" ]

jobs:
  CI:
    name: Build and analyze
    runs-on: windows-latest
    steps:
      - name: Set up JDK 11
        uses: actions/setup-java@v1
        with:
          java-version: 1.11
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0  # Shallow clones should be disabled for a better relevancy of analysis
      - name: Cache SonarCloud packages
        uses: actions/cache@v1
        with:
          path: ~\sonar\cache
          key: ${{ runner.os }}-sonar
          restore-keys: ${{ runner.os }}-sonar
      - name: Cache SonarCloud scanner
        id: cache-sonar-scanner
        uses: actions/cache@v1
        with:
          path: .\.sonar\scanner
          key: ${{ runner.os }}-sonar-scanner
          restore-keys: ${{ runner.os }}-sonar-scanner
      - name: Install SonarCloud scanner
        if: steps.cache-sonar-scanner.outputs.cache-hit != 'true'
        shell: powershell
        run: |
          New-Item -Path .\.sonar\scanner -ItemType Directory
          dotnet tool update dotnet-sonarscanner --tool-path .\.sonar\scanner
      - name: Build and analyze
        env:
          SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
        shell: powershell
        run: |
          dotnet tool install --global dotnet-coverage
          .\.sonar\scanner\dotnet-sonarscanner begin /k:"ViggoSeerden_TTSSimRESTAPI" /o:"viggoseerden" /d:sonar.login="${{ secrets.SONAR_TOKEN }}"        /d:sonar.host.url="https://sonarcloud.io" /d:sonar.cs.vscoveragexml.reportsPaths=coverage.xml
          dotnet restore
          dotnet build --no-restore
          dotnet-coverage collect 'dotnet test ./TTSSimUnitTests/TTSSimUnitTests.csproj' -f xml  -o 'coverage.xml'
          .\.sonar\scanner\dotnet-sonarscanner end /d:sonar.login="${{ secrets.SONAR_TOKEN }}"
      
  CD:
    runs-on: ubuntu-latest
    needs: [CI]
    steps:
      - uses: actions/checkout@v3
      
      - name: Login to registry
        run: >
          echo ${{ secrets.REGISTRY_PASSWORD }}
          | sudo docker login
          -u ${{ secrets.REGISTRY_USERNAME }} --password-stdin
      
      - name: Build image
        run: >
          sudo docker build . --file Dockerfile
          --tag oggiv/fhict-s3-ttssim:backend
      
      - name: Push to registry
        run: sudo docker push oggiv/fhict-s3-ttssim:backend
```

(Job names were altered in this portfolio for the sake of clarity)

At the top of this file I specify when this pipeline gets triggered. This only happens on either a push to the main branch, or a pull request from the main branch. After this, the CI job starts. After specifying the OS to run on and the versions to use, I first setup everything neccessary for the SonarCloud review. At the bottom of this, I specify to what SonarCloud repository the project should be pushed. This required some authentication, and Since typing these directly in my pipeline would be foolish, so I used GitHub secrets for this. This information is referenced by *SONAR_TOKEN*. Then I call *dotnet restore* to restore the package dependencies for each project (this would be *npm ci* for the front-end). After that, I call *dotnet build* (or *npm run build* for front-end) to build the solution. If at any point during the building process an error occurs, this job fails. Warnings get a pass in the back-end pipeline, however in the front-end pipelines warnings get treated as errors, due to this being how React handles the building process. Finally, I call *dotnet test*, followed by the directory for my unit test project (this would be *npm test*), which, as the name suggests, runs the unit tests. These also have to succeed for this job to succeed as a whole.

Since my front-end doesn't have to be pushed to SonarCloud, it's a lot smaller:

```
runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [14.x, 16.x, 18.x]

    steps:
    - uses: actions/checkout@v3
    - name: Use Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v3
      with:
        node-version: ${{ matrix.node-version }}
        cache: 'npm'
    - run: npm ci --legacy-peer-deps
    - run: npm run build --if-present
```

The only commands of note here are *npm ci* and *npm run build*, which do the same as their .NET counterparts that I already explained. There is no test equivalent, since I don't have any tests for the front-end that can be executed in the CI/CD.

Next is the CD job. This job is largely the same between the front- and back-end projects. After once again specifying an OS, I first declare that this job will only run if the CI job is successful. There's no real point in deploying a broken version of my application. This is also why I chose to have my CI/CD process in one file, instead of two seperate files. This CD job deploys my application to DockerHub, which requires some authentication, so I first have to specify my DockerHub username and password. Like in the CI job, it's not safe to put this information directly in the pipeline for the world to see, so there are again handled by GitHub Secrets. These are referenced by *REGISTRY_USERNAME* and *REGISTRY_PASSWORD*. After this, I build my Docker image, by using the Dockerfile in my repository. Finally, after specifying a tag, I push the created image to DockerHub. My front-ends and back-ends are all stored in the same repository under different tags.

I decided to use Docker to deploy my projects to after some recommendations from classmates. Below you can see my back-end Dockerfile:

```
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build-env
WORKDIR /App
COPY . ./
RUN dotnet restore
RUN dotnet publish -c Release -o out
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /App
COPY --from=build-env /App/out .
ENTRYPOINT ["dotnet", "TTSSimRESTAPI.dll"]
```

In this file I first copy everything, which is followed by *dotnet restore* for package dependencies. After that I use *dotnet publish* for building the project and publishing to a folder for deployment. This is finally followed by a few commands to build the actual Docker runtime image.

And here's my Dockerfile used for my front-ends:

```
FROM node:lts-alpine
RUN npm install -g http-server
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build
CMD [ "http-server", "dist" ]
```

This one does simillar things like installing the packages from package.json and building the projects, but I should note the *http-server* install and the creation of the *dist*, which is done to make the app run from Docker.

## Business Process

A business process is a sequence of events that lead to a desired end result, done step by step with possible branching paths leading to different results or extra steps. These can be visualised to get a clear view of the process as a whole, and can help with spotting possible bottlenecks or waste that hinder the efficiency of said process. The visualisation of one is called a Business Process Model and Notation Diagram, or BPMN Diagram for short. With software, a lot of these processes can be optimised even further, through the use of automating parts of a process and storing and accessing data in databases. 

I wanted to try and create a business process for my website. This was easier said than done, since my website isn't one that's used in a professional environment, so it took some creativity to figure out how I should go about doing this. My website doesn't improve any existing processes, since there wasn't any way to play my game before the start of this project (aside from making it yourself from scratch, but that's too farfetched). So, I decided to just make a process that visualises a website visitor, either recurring or new, playing the game, with possible saving and loading of save data and using the game guide on the website: 

![process drawio (3)](https://user-images.githubusercontent.com/100349697/206201530-29770481-daf5-4f57-a5ef-4a050758314d.png)

This process follows a user simply playing the game, with a few branching paths which determine some optional steps. First of all, after a person visits the website, the question arises of whether the visitor has an account. If they do, they log in. If not, they want to create an account. This raises another question: Does this user have a Google account to register themselves with? If they do, they register. If not, they don't. Every path eventually leads to them navigating to the game page. This leads to another split path. If the user is logged in, and has a save file, the save file gets loaded. If not, it gets created on the spot. If the user isn't logged in, they start playing the game as a guest player. During the game, the player might get stuck. Should this be the case, they can navigate to the game guide page, and look up the information that they need to keep playing. Finally, after the user is done playing, and if they are logged in, their game progress gets saved. After this, the user leaves the website, and thus reaches the end of the process. This is a pretty standard process which is entirely defined by the users choices, so there isn't much I could do to improve it. Things I did do to improve the flow of it all is automating the saving and loading systems, and making navigation as clear as possible. 

## Professionalism

### Feedback

Throughout the semester, students are expected to show the teachers their work and ask for feedback on what they've made. Students can, of course, also reach out to teachers when a question arises. No matter the outcome or conclusion of one of these conversations, it's important to document them using Feedpulse on Canvas for possible future reference. This process is also one of the eight learning outcomes. I've shown my work on several occasions to the teachers, and have documented these conversations like expected. An example of this can be found here:

<img width="386" alt="feedpulse" src="https://user-images.githubusercontent.com/100349697/203642711-31b9f335-0571-4e3d-93e6-d1f69349a42d.png">

More examples can be found on Canvas.

### Reflection

I'd like to reflect on some decisions I've made throughout the duration of this semester's IP. Getting the biggest thing out of the way first: The game. Like I mentioned before, I made a game which is playable on my website, however, my way of going about this was far from optimal. I'd spent the first six weeks of the semester developing the game in Unity. The development of this took up way more time than I would've liked to spent on it, let alone the extra time spent debugging and testing. This caused me to pretty much start this semester six weeks in, because the game did nothing for the learning outcomes. I had to make some "sacrifices" to catch back up, such as the idea to use a Java back-end instead of a .NET one. I even neglected asking feedback due to this, since I didn't think asking for feedback would be of any use for the game, since that's not what this semester is about at all. Thankfully I caught back up though. I'd also spent some timme documenting sources used for the development of the game, which wasn't really neccessary either.

Another point of, for lack of a better term, regret, is that I feel like I got a bit too much help from classmates, specifically for setting the CI/CD. I had the whole CI/CD process set up for my front-end before really knowing what it all meant. Had I done more of my own research, it would've taken longer for sure, but I also would've had a way better understanding of it all.

Finally, asking for feedback from the teachers a bit more frequently would've been favorable too. I also received this as feedback from Jean-Paul.

Despite all of this, though, I can't say I'm dissapointed in what I was able to achieve. Game development is something I wanted to learn regardless of my choice of specialisation for semester 4 (which ended up being smart mobile), so getting to do it for a school project was an extra source of motivation to actually do it, even if it did cause some problems. Aside from that, learning how to create an API was fun, and setting up the CI/CD process was interesting and usefull too. UI/UX and some parts of quality assurance were fun to do too. I also think I did a good job keeping my portfolio up to date, once I'd created it. I'm pretty proud of what I did this semester overall.

## Sources

Sources used for the creation of the frontend and backend are found here

- [This video](https://www.youtube.com/watch?v=dGcsHMXbSOA&list=PLDyQo7g0_nsVHmyZZpVJyFn5ojlboVEhE) was used for learning the basics of react
- [This](https://react-unity-webgl.dev/) is React-Unity-WebGL and it's documentation, the React package that allows for Unity WebGL compatability and communication
- Video's 21, 22 and 23 in [this playlist](https://www.youtube.com/playlist?list=PL4cUxeGkcC9gZD-Tvwfod2gaISzfRiP9d) for React routing
- [This bit of code](https://github.com/jeffreylanters/react-unity-webgl/issues/22#issuecomment-1260546499) by a React-Unity-WebGL user for fixing a bug on Unity's end   when navigating to other pages on a site hosting a Unity WebGL game 
- [This video](https://www.youtube.com/watch?v=roxC8SMs7HU) and [this video](https://www.youtube.com/watch?v=75aTZq-qoZk&t=826s), both for setting up a Google           Authentication system
- [This video](https://www.youtube.com/watch?v=Fbf_ua2t6v4) and [this video](https://www.youtube.com/watch?v=Tj3qsKSNvMk), both for learning how to build a RESTful API
- [This Article](https://learn.microsoft.com/en-us/dotnet/core/docker/build-container?tabs=windows) for containerising a .NET app for Docker
- [This Article](https://dotnetthoughts.net/dotnet-minimal-api-integration-testing/) for performing integration tests using an in-memory database in .NET REST API's.

It should be noted that, for some parts of the process of building this project and reaching the desired learning outcomes, I received help from other students or studied other students' portfolio's. Several Canvas modules were used too, but that goes without saying.
