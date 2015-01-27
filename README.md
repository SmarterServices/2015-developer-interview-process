# January 2015 Developer Interview Project (DRAFT)

If you have found this repository it is likely because you are going through the interview process.  

The purpose of this repository is to provide job candidates an avenue to showcase their skills by creating a very simple application based on the specifications outlined here.  

# House Keeping Notes
Please keep these things in mind prior to getting started:

1. To ensure your work cannot easily be copied by other candidates, please do not fork this repository.
2. If you are unsure how to proceed with this repository there is a high chance you do not meet the minimum requirements for this job.  
3. If you make it to the next stage of the interview process, you will be asked to provide a 15-20 presenation of the work completed on this project.  Please keep this in mind as you are putting together your solution.
4. We do not want this project to take up too much of your time so we purposfully made it straightforward.  We estimate this project to take between 4-6 hours of time.

# About the Project

SmarterMeasure is an assessment that quantifies a student's levels of readiness to take an online or technology rich course.  There are mulitple sections of the assessment that students complete, each section has it's own score - there is NOT a composite score as this time.  You may use the login details in the next section if you would like to complete the assessment for yourself so you can understand the context in which you are working.

For this project you will be constructing simple user interface that will display assessment results with the ability to drill in to look at details.  In addition to the user interface, you will need to create a REST API that will serve as a proxy to the SmarterMeasure Mock API.  At the end of this project you will have completed the following:

* Created an interface to display assessment results with associated detail view for each student.
* Built a REST API that interacts with the SmarterMeasur Mock API.
* Using your REST API, added the ability for the user to find a student by their email address - a function that is not currently avaliable in the SmarterMeasure Mock API.

We have provided a visual below to clarify how the final product should be communicating with the SmarterMeasure Mock API.  

1. The user will load the user interface you create
2. Your user interface will communicate directly with the REST API you create.
3. Your REST API will communicate with the SmarterMeasure MOCK API.

```
                            ---------------          --------------------------
Your User Interface -----> | Your REST API | -----> | SmarterMeasure MOCK API  |
                            ---------------          --------------------------
```
**IMPORTANT: The user interface should never call the SmarterMeasure MOCK API directly.**


## Sample Login Credentials

You may use the following credentials if you would like to complete the SmarterMeasure assessment so you can understand the context.

1. Visit [http://decade.smartermeasure.com](http://decade.smartermeasure.com)
2. Click the button that says "Login as First Time User"
3. Choose the username "Development Project"
4. Enter the password "demo"

You will be able to complete the assessment and get your results.

## Requirements

There are really two parts to the project, creating the User Interface and the REST API that the interface will interact with.  The requirements for each are as follows:

### User Interface
The user interface should use [Bootstrap](http://getbootstrap.com/) for the styling as well as a front end framework such as [AngularJS](https://angularjs.org/), [ReactJS](http://facebook.github.io/react/), [JQueryUI](http://jqueryui.com/), etc.  Please choose the framework you are most comfortable with and would choose if you were building a larger scale web application.

### REST API
The API should be built using Node.js, however the structure the application is your decision.  The main thing we will be looking for is a solid understanding of architecting a node application.  You are welcome to choose a [REST API framework](https://www.npmjs.com/search?q=rest+framework) if you wish and use any npm modules you feel are required to complete the task.

### Functionality

The application should have at minimum 2 views/pages.  One view will allow the user to view the assessment results, the other should display a single users results.  

#### Going Above and Beyond

While not required, you are more than welcome to add any additional functionallity you wish to further showcase your skills.  For example:

* A page that outputs statistical information about the user results, etc.
* Unit tests to ensure the application is functioning properly.  This could be done for the REST API and/or the UI.
* Build process to help deployment, install, etc.
* Code linting using [JSLint](https://github.com/reid/node-jslint) or similar.
* ... anything else you come up with.  Feel free to be creative!

### Installing the Deliverable
The deliverable should be easily installed by following an updated version of this README document in your repository.  To provide a standard place to add your project specific install notes, we have provided a section below titled "Candidate Install".



# Connecting to the SmarterMeasure API
For this project we have created a mock API that mimics the actual SmarterMeasure API.  Here are a few things to note about this API:

* To keep things simple, there is no authentication required.
* All the data that is returned is mock/dummy data.

The documentation for the SmarterMeasure API is located at [https://github.com/SmarterServices/2015-developer-interview-project/blob/master/API.md](https://github.com/SmarterServices/2015-developer-interview-project/blob/master/API.md)


# Candidate Install
Please edit this section providing any documention required to get your version of the install running.  This should include the following:

* How to install the app.
* How to run the unit tests.
* How to run the server, if different from the default method provided.

# Questions?

If you have any questions regarding the requirements or have issues you have two ways to contact us for help:

* Email Jason at jason@smarterservices.com.  
* Tweet us [@SmarterDevTeam](https://twitter.com/SmarterDevTeam)
