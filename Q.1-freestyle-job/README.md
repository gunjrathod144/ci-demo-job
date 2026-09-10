Q1 Explanation

Project Name: ci-demo-job is the name of the Jenkins Freestyle job we created.

SCM: SCM means Source Code Management. We connected Jenkins with our public Git repository so Jenkins can get the latest code.

Build Step: After getting the code, Jenkins runs the required commands to install dependencies and execute the tests.

Trigger — Poll SCM: We selected Poll SCM so Jenkins can automatically check GitHub for new changes.

Why Poll SCM: Our Jenkins server is not publicly accessible, so GitHub cannot directly send a webhook to Jenkins. Poll SCM solves this by making Jenkins check the repository itself.

H/5 * * * *: This tells Jenkins to check the Git repository approximately every 5 minutes. If a new change is found, Jenkins starts a build.
