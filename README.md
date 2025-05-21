Jenkins:
    In this Task, If any one of the development department are merge code to the main branch then, 
    Jenkins are triggered and tell the newby code of that.

Process:
    First, create a file named Jenkinsfile in this repository and write proper script for that.
    After, setting --> Webhooks --> put payload url like this 
            payload url --> "http://<your-ec2-public-ip>:8080/github-webhook/" 
            Content type --> application/json
            tick --> Just the push event
    Do process on Jenkins like, create pipeline and put link of this git repository

Outcome:
    after doing this, when developer merge to the main branch their code, Jenkins will triggered and
    create build and print the merged code in jenkins