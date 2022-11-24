# Individual Project: Tartarus Simulator
### By Viggo Seerden 
Student no. 491216

![tartarussimlogo](https://user-images.githubusercontent.com/100349697/203649141-82c8d347-ebd5-444a-acef-820b5f7d6168.png)

## Table of Contents

- [Project Description](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#project-description)
  - [Technology Stack](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#technology-stack)
- [Documentation](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#documentation)
  - [User Stories](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#user-stories)   
  - [C4 Model](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#c4-model)
- [UI/UX](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#uiux)
- [Quality Assurance](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#quality-assurance)
  - [Code Analysis](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#code-analysis)
  - [Testing](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#testing)
  - [Performance](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#performance)
  - [Security](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#security)  
- [Release Management](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#release-management)
  - [Version Control](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#version-control)
  - [Branching](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#branching)
  - [CI/CD](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#cicd)
- [Ethics](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#et)
- [Professionalism](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#professionalism)
- [Sources](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/IndividualProject.md#sources)

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

To give each player a way to save their own progression, I made a saving system in Unity that saves a players’ progress to a JSON file. 
The contents of this file can easily be saved to an external SQL database that both the game and the website can access. 
These save files can also be encrypted to prevent anyone from cheating and manually altering the save file.

### Technology Stack
This project (as of now) consists of two React frontends, one of which is an admin frontend, a .NET backend, and an SQL database. My choices for these options are as follows:

For the frontend, I chose to use React.JS. Personally, I've never worked with a JavaScript-based frontend (or backend, for that matter), 
so I had no experience or knowledge about any possible option. React, along with Vue and Angular, where the example/recommended options listed on Canvas, 
so I decided to choose one of these three. After I thought of the initial idea behind my project, 
I did some research into each of these options and their compatability with Unity WebGL games. I quickly found React-Unity-WebGL, 
a package for React that gave me everything I'd need, with a clear, 
straight to the point documentation that even a newcomer like me could understand on it's installation, uses and functions. Aside from this, 
React was the only one I'd heard of before, and it was often recommended by others, so this choice was easy for me to make.

Below is a picture of the frontend/website:

<img width="941" alt="site" src="https://user-images.githubusercontent.com/100349697/203651773-c6737cf1-4e6f-4d63-98b4-6f2b70313b26.png">

For the backend, I originally wanted to go with Java. Like with the frontend, I looked at the recommendations on Canvas for this one. 
I'd already used the other recommendation, .NET/C#, in both Semesters 1 and 2 for pretty much everything, so I thought it'd be nice to learn another language.
After a few weeks of developing the game, and doing some research on Java, I changed my mind on this. I had already spent a good amount of time on the game,
so I had some catching up to do for the rest of the project. It's because of this that I ended up going with .NET instead. I was gonna need my time, 
since I didn't just have a website/frontend and API/backend to build from scratch, but also a reasonably big game to make.
My previous experience with .NET would make developing the backend a whole lot quicker, so that's what ended up being used. I should also quickly mention the game. Since it's made in Unity, the scripts are written in C#. This is the standard language Unity uses, so I stuck with it. But this was another reason for me to use .NET for my backend API, since I could use the same save data classes and even some logic that I used in the game without issue. This made some user stories a lot easier to realise, and ended up saving me a lot of time.

Below is a picture of the API's Swagger page:

<img width="941" alt="swagger" src="https://user-images.githubusercontent.com/100349697/203651788-a0f4b355-36d3-4c54-bb5c-404de9b91760.png">

Finally, this back-end is connected to an SQL database. I access and alter the data in there using Entity Framework as my ORM of choice in my back-end. This is due to past expecience with it from my group project in semester 2, and also due to a good amount of recommendations online after some quick research. This back-end is currently only available locally on my laptop, where I use SQL Server to access it.

## Documentation

### User Stories
Below are the user stories I made. These are for the website, not for the game, since the game isn't a required product for this semester. I chose to write user stories instead of requirements due to them being more flexible compared to requirements.
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

<img width="853" alt="trello" src="https://user-images.githubusercontent.com/100349697/203642404-81dc53ed-580b-4d45-9bdf-01a470eec58c.png">

#### Prioritization
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

## Quality Assurance

### Code Analysis

### Testing

Currently, I have written a few unit and integration tests for my back-end through two MSTest projects in the same solution as my back-end. 

The unit tests test the save data alteration I do in my back-end's service classes, which is pure logic. An example can be found below:

<img width="564" alt="unit test" src="https://user-images.githubusercontent.com/100349697/203649883-61447b46-c04d-4d5f-89c3-50d1b0d439fd.png">

In this test, I simulate buying an item, and thus testing the logic behind adding this item to the save file, while also making sure to subtract the correct price from the users balance. This is all checked at the end. 

My integration tests test the connection to the back-end, and by extension the database. An example can be found below:

<img width="651" alt="integration test" src="https://user-images.githubusercontent.com/100349697/203650269-db2ff834-3632-4a38-9b86-6220f791e3a0.png">

In this test, I simulate the process of adding a new user to the database. This is possible thanks to a NuGet package called Microsoft.AspNetCore.Mvc.Testing, which allows me to emulate an http request, which can then access the correct function in my controller, which executes the code like normal. I then check the response by first converting it to a more readable string format, and then checking if it contains the correct data. I also check for the correct status code.

### Performance

So far, I have checked my front-end performance using Google Lighthouse:

<img width="301" alt="lighthouse" src="https://user-images.githubusercontent.com/100349697/203652520-90346590-e417-43cd-9b02-e40b8e42c15c.png">

The performance score used to be much lower, due to me using a less optimal image file for the logo on the main page, which had such a heavy impact on the performance that the score used to be a 6.3. After fixing this, however, there remain few optimisations to be made.

### Security

My website relies on accounts to work properly, since I want every user to have their onw save file for the game. This means my website needed some form of authentication. I decided to use Sign in with Google for this. Being able to create accounts using Google means that pretty much most people nowadays can easily create an account due to Google's popularity. The Sign in with Google feature itself is also incredibly popular, which meant proper documentation was easily accessible. But I also chose this for security reasons. There's simply no way I can create a more secure login system by myself with my current knowledge and time constraints. Google is also a trusted name worldwide. There are a few downsides to this, though. First of all, any potential users would have to trust me not to misuse their data, which is easier said than done, however, since I have no plans of publicly launching this website, that's not a concern. But aside from that, I have to rely on Google to keep my system working as expected. If Google were to go down, even just temporarily, my webiste would lose over half of it's functionality. I'm not worried about this, since I doubt something as big as Google's servers and databases and whatnot would go down so easily, but it is a risk nonetheless. There's also the risk of Google deciding the Sign in with Google feature is no longer needed and pulling support for whatever reason, and them either creating a new system entirely, or not making one anymore at all. Replacing an existing system with a new one has already happened fairly recently with OAuth 2.0, whose days of support are numbered. But the chances of this happening anytime soon are incredibly low, so i'm not worried about that either. As you can see, to me, the good easily outweighs the bad, so I think Sign in with Google was a good option to go with.

Aside from this, I have implemented a security measure within the Unity project, which gives me the option to encrypt save files before saving them. This is done using X-OR encryption.

## Release Management

### Version Control

I have been using GitHub repositories as my version control system of choice, one each for both front-ends and the back-end. Below is an example of one of my GitHub repositories:

<img width="792" alt="github frontend" src="https://user-images.githubusercontent.com/100349697/203647973-12b4aa5d-4b2a-4f13-9ec2-b84d49cd229f.png">

I chose to use GitHub due to my previous experience in using it during last semesters' group project, and due to it's popularity. As for branching, at the time of writing this, every repository has two branches: main (or master), and develop. The develop branch is for developing new features. This is done so that, in the case that something goes wrong, I always have a stable version to go back to on the main. The main branch only gets pushed to once I'm sure any changes I made work as intended on the develop branch. Once something gets pushed to the main, the CI/CD gets activated. More on that below.

### CI/CD

I have created a CI/CD pipeline using GitHub Actions for every repository. Below is an example of the back-end pipeline:

```
name: CI/CD

on:
  push:
    branches: [ "master" ]
  pull_request:
    branches: [ "master" ]

jobs:
  CI:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    - name: Setup .NET
      uses: actions/setup-dotnet@v3
      with:
        dotnet-version: 6.0.x
    - name: Restore dependencies
      run: dotnet restore
    - name: Build
      run: dotnet build --no-restore
    - name: Unit test
      run: dotnet test ./TTSSimUnitTests/TTSSimUnitTests.csproj
      
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

At the top of this file I specify when this pipeline gets triggered. This only happens on either a push to the main branch, or a pull request from the main branch. After this, the CI job starts. After specifying the OS to run on and the versions to use, I first call *dotnet restore* to restore the package dependencies for each project (this would be *npm ci* for the front-end). After that, I call *dotnet build* (or *npm run build* for front-end) to build the solution. If at any point during the building process an error occurs, this job fails. Warnings get a pass in the back-end pipeline, however in the front-end pipelines warnings get treated as errors, due to this being how React handles the building process. Finally, I call *dotnet test*, followed by the directory for my unit test project (this would be *npm test*), which, as the name suggests, runs the unit tests. These also have to succeed for this job to succeed as a whole.

Next is the CD job. After once again specifying an OS, I first declare that this job will only run if the CI job is successful. There's no real point in deploying a broken version of my application. This is also why I chose to have my CI/CD process in one file, instead of two seperate files. This CD job deploys my application to DockerHub, which requires some authentication, so I first have to specify my DockerHub username and password. Since typing these directly in my pipeline would be foolish, so I used GitHub secrets for this. These are referenced by *REGISTRY_USERNAME* and *REGISTRY_PASSWORD*. After this, I build my Docker image, by using the Dockerfile in my repository. Finally, after specifying a tag, I push the created image to DockerHub. My front-ends and back-ends are all stored in the same repository under different tags.

I decided to use Docker to deploy my projects after some recommendations from classmates. Below you can see my back-end Dockerfile:

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

Currently, tests are only done in the back-end pipeline, since there are no front-end tests made yet. Furthermore, only the unit tests get executed, because the integration tests are currently impossible to successfully perform since my database is only locally available.

## Ethics

## Professionalism

Throughout the semester, students are expected to show the teachers their work and ask for feedback on what they've made. Students can, of course, also reach out to teachers when a question arises. No matter the outcome or conclusion of one of these conversations, it's important to document them using Feedpulse on Canvas for possible future reference. This process is also one of the eight learning outcomes. I've shown my work on several occasions to the teachers, and have documented these conversations like expected. An example of this can be found here:

<img width="386" alt="feedpulse" src="https://user-images.githubusercontent.com/100349697/203642711-31b9f335-0571-4e3d-93e6-d1f69349a42d.png">

More examples can be found on Canvas.

## Sources

Sources used for the creation of the frontend and backend are found here

- [This video](https://www.youtube.com/watch?v=dGcsHMXbSOA&list=PLDyQo7g0_nsVHmyZZpVJyFn5ojlboVEhE) was used for learning the basics of react
- [This](https://react-unity-webgl.dev/) is React-Unity-WebGL and it's documentation, the React package that allows for Unity WebGL compatability and communication
- Video's 21, 22 and 23 in [this playlist](https://www.youtube.com/playlist?list=PL4cUxeGkcC9gZD-Tvwfod2gaISzfRiP9d) for React routing
- [This bit of code](https://github.com/jeffreylanters/react-unity-webgl/issues/22#issuecomment-1260546499) by a React-Unity-WebGL user for fixing a bug on Unity's end   when navigating to other pages on a site hosting a Unity WebGL game 
- [This video](https://www.youtube.com/watch?v=roxC8SMs7HU) and [this video](https://www.youtube.com/watch?v=75aTZq-qoZk&t=826s), both for setting up a Google           Authentication system
- [This video](https://www.youtube.com/watch?v=Fbf_ua2t6v4) and [this video](https://www.youtube.com/watch?v=Tj3qsKSNvMk), both for learning how to build a RESTful API
- [This Article](https://learn.microsoft.com/en-us/dotnet/core/docker/build-container?tabs=windows) for containerising a .NET app for Docker
