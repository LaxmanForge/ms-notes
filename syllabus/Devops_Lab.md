	![](https://lms.cuchd.in/theme/image.php/moove_child/page/1784867403/monologo?filtericon=1)

# Course Syllabus and Suggestive Readings

1. [CONT_25CAP-732 :: DEVOPS PROCESS AUTOMATION LAB](https://lms.cuchd.in/course/view.php?id=124359&section=0 "CONT_25CAP-732 :: DEVOPS PROCESS AUTOMATION LAB")
2. [Course Overview](https://lms.cuchd.in/course/view.php?id=124359&section=0)
3. Course Syllabus and Suggestive Readings

## Course Syllabus and Suggestive Readings

Completion requirements

**Course Syllabus**

|                                                                            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                      |                |
| -------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | -------------- |
| **Unit-1**                                                                 | **Introduction to SCM and Build Tools**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | **Lecture Hours:20** | **Co Mapping** |
| Experiment 1                                                               | Install and setup git in your systems. <br><br>a. Create a python file named as your UID (eg.22MCC20001.py) with some code inside it on a Local Repository named as your UID (eg. 22MCC20001). Push this file on Remote Repo.<br><br>b. Create a another Local Repository named as your name (eg. ABC) and pull the files from Remote Repo in it. After this, create a new file in new Local Repo i.e. ABC and push it to Remote Repo. Again pull the files on old Local Repo i.e. 22MCC20001.<br><br>c. At last, visit Remote Repo and commit some changes in a file created i.e. 22MCC20001.py and pull the file again in new Local Repo i.e. ABC. Check whether the changes are existing in the file in Local Repo or not.                             |                      | CO1            |
| Experiment 2                                                               | a. Create a new file named UID_Name.txt in your local repo and add some content in the file and push it to the remote repository.<br><br>a. Manage to create a two new branches using Git. Two branches must be named as your UID and Name respectively.<br><br>a. Now, after creating branches, UID_Name.txt file must be available in Branch UID. Make some changes in the file present in Branch UID.<br><br>a. After this, come back to your Master branch and merge the file with Branch UID file. If you face any conflicts, remove it **using proper conflict resolution strategy**.<br><br>a. Create a new file named as Name.txt in Branch Name. Now try to merge it with Branch UID file. Will it be merged or not? Show after implementing it. |                      | CO2, CO3       |
| **Unit-2**                                                                 | **Introduction to** Maven                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                      |                |
| Experiment 3                                                               | With an understanding of the theory and techniques that Maven uses to manage a project, we can now develop our own Maven project.<br><br>In this application, you have to create a simple adder that computes the sum of two integers. During this process, you will:<br><br>a. Generate a Maven project using the Maven command-line tool<br><br>b. Configure the pom.xml file<br><br>c. Create main and test source code files<br><br>d. Execute a Maven build<br><br>e. Execute the resulting JAR file                                                                                                                                                                                                                                                 |                      | CO2            |
| Experiment 4                                                               | a. Install and configure Jenkins and Java 17.<br><br>b. Creating admin Jenkins user and touring the Jenkins dashboard.<br><br>**c.** **Configure Global Tool Configuration for Maven and Git.**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                      | CO2, CO4       |
| **Unit-3**                                                                 | **Introduction to Jenkins**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                      |                |
| Experiment 5                                                               | Create a Jenkins Freestyle Project which consists of Maven Build jobs.<br><br>Note: Trigger the builds of all the Maven 9 Goals. **Enable build triggers using Poll SCM or Webhook**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                      | CO3            |
| Experiment 6                                                               | f. Write a Scripted Pipeline to execute the build pipeline with all the 9 goals of Maven.<br><br>f. Execute the Scripted Pipeline via Scripted Pipeline with SCM. Name the file as Jenkinsfile and build a pipeline.<br><br>g. **Convert Scripted Pipeline to Declarative Pipeline**                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                      | CO3            |
| **Project Based on the contents of unit-I, II, III**                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                      |                |
| Experiment 7 <br><br>Experiment 8<br><br>Experiment 9<br><br>Experiment 10 | **Project 1:** Develop a simple Java Maven application and implement an automated CI pipeline using Git and Jenkins to build, test, and generate artifacts.<br><br>**Project 2:** Configure Apache service using Puppet and deploy Nagios via Docker to automate infrastructure setup and monitor service health.                                                                                                                                                                                                                                                                                                                                                                                                                                         |                      | CO4, CO5       |

**Textbooks / Reference Books**

**Text Books:**

**T1**. Michael Duffy, DevOps Automation Cookbook, 3rd Edition (2023).

**T2.** Joakim Verona **,** Practical DevOps Automation, 2nd Edition (2023).

**Reference Books:**

**R1.** Kief Morris**,** Infrastructure as Code: Managing Servers in the Cloud, 3rd Edition (2023).

**R2.** Stephen Fleming**,** DevOps Tools for Automation and Scaling, 2nd Edition (2022)

**Book Purchase Link :**

[https://www.amazon.com/DevOps-Automation-Cookbook-Michael-Duffy/dp/1784392820](https://www.amazon.com/DevOps-Automation-Cookbook-Michael-Duffy/dp/1784392820)

[https://www.amazon.in/Practical-DevOps-organization-effectively-monitoring/dp/1788392574](https://www.amazon.in/Practical-DevOps-organization-effectively-monitoring/dp/1788392574)

Last modified: Monday, 29 June 2026, 4:08 PM

✨ Summarise✨ Explain

Previous activity




MST -1
 important topics
1. Basics of testing 
   ```
   Define software testing
   objective of testing
   types of testing
   how testing is differnet from continous testing
   what are the objectives of continous testing
   Write a flow where a continous testing is imbedded into devops lifecycle/ dovps sdlc
   benefits features and advantages of continous testing
   write the 5 tools for performing testing
   ```
   2. Devops test Stratergy
      ```
      flow [same question]
      Define dev sec ops
      what are the different parameters and policies of securtiy in dev sec ops
      what is VCS [ version control system]
      Typs of VCS
      Git is distributed vcs justify it.
      Write down the steps for installing git in Linux /centos / ubuntu [answers will        be diferetn on all these specially package managers]  - star
      How to create local repository and remote Repository [Properly]
      How git is contributing in building the code
      Write down the steps for installing git in windows
      
      howt to connnect and hot to remove local repository
      what is git branching
      what is the role of branch
      what are the merege conflicts [ wirte down at least 5 conflicts that occur             using git merege]
      Create a first branch [scanrio based questions] then       - star
      
      what is jenkins and why it is ci/cd tool
      what is jenkins build server
      and write a whole process with which jenkins build server is working
      write down the steps for setting a maven insdie the jenkins. Explain the role of       pom.xml in managing the dependencies     -star
      what is artifact and its role in  jenkins process
      how jenkins build server is managing the jenkins build test and deploy processes
      Demonstrate the steps for triggering the build using external links and justify        its role in jenkinsautomation.
       how to change the jobs in jenkins  - star
       explain how autoamtion can be achieved by changing the jenkins projects - star
       what is jenkins cli and wrtie doen the steps for manging the jenkins via               jenkins cli 
      ```



important Security checks! followed in  dev sec ops
```
1. Code Security 
   SAST - it basically checks the source code
   
   Library Security - existence of libraries will be check it is called dependecy       scanning DAST
   
   Password security - secretly scannning is there password api key tokens and          credentials 
   
   Application Security -  it checks the running of complete application 
   
   
   role of jenkins in implementing dev sec ops - star
   
```
in ci/cd if u get an error if it get resolve it will get tested and it il be depolyed but in dev sec ops if u get a pause in security checks then? -star