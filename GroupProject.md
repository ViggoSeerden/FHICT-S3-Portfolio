# Group Project: iO Colleague Tracker
### By Viggo Seerden (In Collaboration with Abe van der Werf, Josian van Efferen, Niels Feijen & Vincent Vermiere)
Student no. 491216

<img alt="io" src="https://user-images.githubusercontent.com/100349697/203783153-01b59778-a7cd-4ece-a499-039884d3965d.png" width="50%" height="50%" />

## Table of Contents

- [Project Description](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/GroupProject.md#project-description)
- [Documentation](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/GroupProject.md#documentation)
- [Agile](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/GroupProject.md#agile)
- [UI/UX](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/GroupProject.md#uiux)
  - [UI](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/GroupProject.md#ui)
  - [UX](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/GroupProject.md#ux)
- [Release Management](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/GroupProject.md#release-management)
- [Ethics](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/GroupProject.md#ethics)
- [Business Process](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/GroupProject.md#business-process)
- [Professionalism](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/GroupProject.md#professionalism)

## Project Description

For company iO, we made a colleague tracker application for Android & iOS. In here, iO employees can keep track of where their colleagues are, should they need them for something. This means being able to see whether they're at home, or at one of their offices, and possibly even which floor or room they're in. You could also be able to see their availability through Outlook agendas. If you need a colleague, you can notify them, and you can also bookmark some colleagues for quick access. Staff locations could also be automatically updated based on MAC-addresses and/or WiFi logs.

## Documentation

I made several user stories for the project, which are listed below:

- US1: As an iO staff member, I want to see whether my colleagues are working from home or the office so I know where to look if I need them
- US2: As an iO staff member, I want to set my current availability in the app so that my colleagues know whether I’m busy and can reach out or not
- US3: As an iO staff member, I want to be given a choice of whether I consent to sharing my location with others for my own privacy
- US4: As an iO staff member, I want to see on what floor or in what room my colleagues currently are so I know exactly where to find them
- US5: As an iO staff member, I want to have the ability to add the MAC-Addresses of my other devices so my location can be updated based on multiple sources
- US6: As an iO staff member, I want to be able to search for specific colleagues in the app using name input or a selection of filters so I can find someone suitable    faster
- US7: As an iO staff member, I want to be able to see the agenda of my colleagues so I can see their full availability
- US8: As an iO staff member, I want to be able to notify my colleagues so they know that I need them and that I’m looking for them
- US9: As an iO staff member, I want to be able to create my own profile page with a name, e-mail address, description and role/specialty so others know how to reach     me and if I’m suitable for their request
- US10: As an iO staff member, I want to be able to see the profiles of my colleagues so I know where I can reach out to them, and whether their role suits my request
- US11: As an iO staff member, I want to be able to post an open request so that anyone with time can come and help
- US12: As an iO staff member, I want to be able to bookmark or favorite certain colleagues for easy access in the app should I need them multiple times in the future
- US13: As an iO staff member, I want to receive a notification when an unavailable colleague I need becomes available again
- US14: As an iO staff member, I want the app to be written in English so that everyone can use the app without a language barrier
- US15: As an iO staff member, I want the app to be compatible with both iOS and Android, so that everyone with one of those OS’s can use the app
- US16: As an iO staff member, I want the app to boot and load new pages in no more than 3 seconds to keep the workflow going smoothly
- US17: As an iO staff member, I want my data to be properly protected so no one has access to it.
- US18: As an iO staff member, I want to be able to refresh the data so I can check if any changes have been made to my colleagues statuses
- US19: As product owner, I want every staff member to be able to log into their account so that outsiders cannot access their data

To keep track of the progression of these user stories, as wel as other tasks, we made use of Jira. More on this can be found under Agile.

## Agile

We made use of Scrum for this project. Our project was split into 5 sprints of 3 weeks each, starting with sprint 0. This includes daily stand-ups and stand-downs, and presentations and retrospectives with our stakeholders and teacher at the end of every sprint. We also made use of Jira for keeping track of our progression on user stories and tasks, but also as a means of communication with our stakeholders at iO. We would use the comments on Jira tickets to ask questions or feedback. Jira also has other tools available for us to use suck as sprint burndown charts. To make proper use of this chart, we also started making estimations for how long issues would take us to do, and keeping track of how long each issue actually ended up taking us to complete. We chose to use Scrum due to everyone having prior experience with this framework. 

Here is a picture of our Jira Backlog from Sprint 3:

<img width="1262" alt="jira" src="https://user-images.githubusercontent.com/100349697/203783393-272a9c52-05b8-49f5-84a4-19707452cf9f.png">

## UI/UX

It's important that we make this application as accessible and user friendly as possible for the best result once it gets incorperated into iO's business, while also making sure it fits their brand identity.

### UI

I mainly worked on the front-end for this project. While I didn't make the base designs for the applications' different screens, I did translate them into a functional application, while also influencing and altering the existing designs, and taking some creative liberties here and there. The UI is pretty straight forward here. iO provided us with a bunch of branding material which were used to style the application. Their main colors were orange and blue/purple with white, and after presenting some designs with the colors used in different area's to the stakeholders at iO, this ended up being the final design for the color layout:

<img width="206" alt="io home" src="https://user-images.githubusercontent.com/100349697/206261412-d3d5a1ae-fd46-4db8-b687-bc72d4a14150.png">

The orange was chosen to be the main color in the background, with a white navbar and text, and the purple was used for most buttons.

### UX

The application consists of three main pages, those being the colleague page, the profile page and the settings page. Navigation is handled by a tab bar on the bottom of the screen, with text and icons to make it clear which button leads to which page. There are some pages hidden under the settings tab, those being the profile settings, notification settings, MAC-address management, and terms & conditions, but these aren't the main focus of the app, hence why they aren't accessible through the tab bar, as it would feel cluttered otherwise.

Several measures were taken to improve the experience within the app. I'll go over a few examples that I am responsible for implementing. First of is the mail verification screen:

<img width="206" alt="io mail confirm" src="https://user-images.githubusercontent.com/100349697/206263859-fa954016-4b1f-43d3-bf54-699b9bf883c6.png">

First of all, it's worth mentioning that the tab bar is not visible on any of the login related pages, as this would remove the need to log into the application, and allow users to see others' locations without sharing their own. However the main focus here is on the input fields and the button at the bottom. The button to submit your input for verification remains disabled until the input is valid, which is visually indicated as well, since the style changes when input is detected: 

<img width="174" alt="io mail confirm input" src="https://user-images.githubusercontent.com/100349697/206264755-dc9e2b70-08f2-40b0-b693-7727e72a3b18.png">

The terms and conditions are also accessible via the link in the checkbox text. This is of the utmost importance, because the user should be aware of how their data is handled. Like mentioned earlier, these terms and conditions can also be found after logging in under the settings page.

More examples can be found on the profile screen:

<img width="206" alt="io profile" src="https://user-images.githubusercontent.com/100349697/206265687-c12ef0c3-3cc5-48e9-b5e0-b3399ea57000.png">

First off, the time selection wheels labeled start and end at the bottom limit your selection based on what time was selected in the opposite input field:

<img width="154" alt="io profile time" src="https://user-images.githubusercontent.com/100349697/206266293-831f431e-ad9b-4592-91c1-de4bd84b8cbe.png">

This was done to avoid any invalid input. However, should invalid input still occur somehow, an error message will be displayed:

<img width="129" alt="io profile error" src="https://user-images.githubusercontent.com/100349697/206266649-88bbfba4-7409-4698-ad30-662f6052c56f.png">

Updating time doesn't happen automatically, so there's a button to do just that. This button remains hidden until you change your time input, but only if the input is valid:

<img width="101" alt="io profile time button" src="https://user-images.githubusercontent.com/100349697/206266980-209aa1f9-7efa-4894-a77d-c8bc64557ef6.png">

Finally, there's the location toggle button:

<img width="129" alt="io profile status button" src="https://user-images.githubusercontent.com/100349697/206267050-08d5f3d7-6761-44b8-ade2-8c3ecaed73e8.png">

It was quite difficult to find the right style to use for this button. We had several other designs for it, which all got some criticism from our stakeholders for not being clear on what option was actually selected, and which one could be pressed. This also sparked some discussion within our team, since we had some conflicting idea's of how it should be done. Since it was my task to fix said button, I did some quick research on toggle buttons of the sort, and quickly found that these types of buttons tend to be a challenge for most people. Eventually, I came up with the design seen above, which everyone agreed upon. This design was inspired by these types of toggles commonly found on iOS devices:

<img width="129" alt="io profile status button" src="https://user-images.githubusercontent.com/100349697/206267821-bab000a4-ca2a-4404-b81a-4120bb794c2f.jpg">

Finally, it should be noted that the final design still consists of two seperate buttons right next to each other, instead of one toggle component. The selected option will be disabled, to avoid any duplicate API calls to the back-end.

## Release Management

We made a GitHub repository for both our front- and back-ends. Both have a multitude of branches made. Aside from the main, we have a release branch, and several branches for different functions still in development. 

Below is a picture of our front-end GitHub repository:

<img width="1049" alt="github gp" src="https://user-images.githubusercontent.com/100349697/203785032-0d4c6c90-3704-4c10-a515-08d7c8e75e30.png">

## Ethics

The ethical aspects of your project shouldn't go ignored during development, since in a lot of cases, you're releasing your product for a number of people, big or small, to use. This can include respecting a users privacy and security, properly handling their data and being transparent about your way of doing so, and being considerate of both colleagues and end users.

In the case of this application, we are handling with possibly sensitive user data, including personal info, digital info, and location data which can be automatically determined. At the start of this project, we received a legal document that details several measures that were taken for ethics' sake. Aside from this document, however, we ourselves also had to implement some features that support the morality of handling and exposing the data within the app, which were discussed with our stakeholders.

First of all, like I mentioned under the section about UX, the terms and conditions are accessible both before and after logging into the application. Transparency is important when it comes to handling a potential users' data. These terms and conditions were provided to us by our stakeholders. You will only be able to log in and use the application after accepting these terms and conditions. By doing so, it means agreeing that your location will be visible to your colleagues. Once logged in, you will be able to see the locations of colleagues that also use the apps, and they will be able to see yours too. If you don't want your location to be shared with others, it would be entirely unfair if you could still see theirs, so there is no such option.

Logging into the app is only possible after getting your email verified. This alone doesn't mean much, since everyone can try entering their email address and get it verified, but that wouldn't be safe, since the app is meant only for iO staff to share their location with each other, and no one else outside the company. It's because of this that we've made it so that the email that's entered is checked before sending a verification link. iO has their own email format, that being *staffname @iodigital.com*. If the entered email doesn't have the *@iodigital.com* suffix, it won't receive a verification link, which means you can't advance any further with logging in. However, all this isn't even possible if you don't make it past the first screen of the app. Our app also uses Sign in with Google as an extra layer of security. This will be your method of logging in after registering. 

Finally, each user get's their own unique identification token after registering. This token is used in every API call made, and is checked in the back-end every time before returning any data. This is, again, to prevent unauthorized access to user data. 

(AWS WIP)

While our group didn't ever decide we'd commit to any specific list of ethical software development principles, like those by ACM or Adam Scott, we do still abide by a good amount of them. These principles detail aspects like e.g accessibility, privacy and security, and consideration for colleagues and peers. I've already covered privacy and security, but the others shouldn't be ignored. For example: Accessibility. I've already detailed some aspects of the application which do just this under the UX section. Keeping your fellow programmers in mind is also of importance according to these principles, through helping them where neccessary, treating each other with respect, or through the use of features such as documentation and version control. We have made several pieces of documentation for this project, and like mentioned above, we used GitHub as a version control system. Within our team, we all also had to work with each others code at one point or another, so explaining our code to each other where neccessary was done frequently, whether that be through verbal or digital means.

## Business Process

(WIP)

## Professionalism

Throughout the semester, students are expected to show the teachers their work and ask for feedback on what they've made. Students can, of course, also reach out to teachers when a question arises. No matter the outcome or conclusion of one of these conversations, it's important to document them using Feedpulse on Canvas for possible future reference. This process is also one of the eight learning outcomes. I've shown my work on several occasions to the teachers, and have documented these conversations like expected. For the group project, we also have group and peer feedback, which are usually done at the end of a sprint. Finally, and probably most importantly for the group project, we also need to have frequent contact with the project stakeholder, in our case the people from iO. Like mentioned above, this was mainly done via Jira in the comments of issues, but also during our sprint retrospectives at iO's offices in Eindhoven.

An example of feedpulse from a GP product can be found here:

<img width="641" alt="feedpulse GP" src="https://user-images.githubusercontent.com/100349697/203783530-ef620494-098b-411d-ae08-c07e1ca8c157.png">

More examples of this can be found on Canvas.
