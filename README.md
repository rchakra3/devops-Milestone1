# M1 - Milestone 1

## Team details
### Name: Raptors
### Team members
+ Sagar Muchhal (srmuchha)
+ Vinay Suryadevara (vksuryad)
+ Rohan Chakravarthy (rchakra3)
### Individual contributions
***Sagar Muchhal***: Setup the Jenkins server on the droplet and the Maven project that is being used for the build pruposes. Helped with the documentation.

***Vinay Suryadevara***: Setup the maven project and helped with the jenkins server and recorded the screencast for the demo.

***Rohan Chankravarthy***:


This milestone required us to configure/build a build server. We have setup the Jenkins build server on a DigitalOcean droplet. The following plugins were installed onto the Jenkins server:
1. Github plugin: This enables the Jenkins server to communicate to remote Git repositories.
2. Email-ext plugin: This enables the Jenkins server to shoot emails based upon the status of builds such as SUCCESS, FAILED etc.

The project that we are using for this milestone is a simple Maven project which has a unit test associated with it. The steps to setup the Maven project were taken from [here](http://www.mkyong.com/maven/how-to-create-a-java-project-with-maven/). After a successful build, the unit test case gets executed and the result of the test case execution is displayed on the UI of the Jenkins job.

## Jenkins Build server

Jenkins server performs the following tasks:
### Ability to trigger a build 
In response to a commit in a particular branch, a new build is started on the Jenkins server. We have configured two Jenkins jobs specific to two branches *master* and *dev*. Whenever a commit is pushed to a particular branch, the Jenkins job pulls the fresh code and a build specific to that branch is triggered.

### Ability to execute a build job via a Build Manager
Since the project that we are using is a Maven project, Maven takes care of initiaiting a clean build every time the job is executed. The Jenkins job automatically runs the Maven command:
```
mvn clean install
```

### Determine success or failure of a build job
The status of the build is displayed on the Jenkins UI in the Build History tab specific to the job. The color against the build indicates the status of the build, Red for Failure or Blue for Success and Yellow for Test Failure.
Post build, an email regarding the status of the build job is sent to the specified recipients. The plugin Email-ext was used for this purpose.

### Build multiple branches of the repository
We have setup two separate Jenkins jobs pertaining to the `master` and `dev` branches. Whenever a commit is pushed to a particular branch, the job specific to that branch gets initiated. We have shown this a part of the milestone screencast.

### Track of past builds
The Jenkins UI shows the status of the past builds that were triggered against that job. It also shows the color coded status of those jobs and clicking on an individual build would give the details specific to that build.

## Jenkins Configuration file 

## Screencast and code 
The screencast can be found at the following [URL]() and the Maven project code is present in the same repository
