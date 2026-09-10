Q1 Explanation

Project Name: ci-demo-job is the name of the Jenkins Freestyle job we created.

SCM: SCM means Source Code Management. We connected Jenkins to our public GitHub repository so it can get the latest version of the project.

Build Step: We used build.sh as the build script. Jenkins gives permission to execute it and then runs ./build.sh. The script contains the required dependency/setup and test commands.

Trigger — Poll SCM: We selected Poll SCM so Jenkins regularly checks GitHub for new changes.

Why Poll SCM: Our Jenkins server is not publicly accessible, so GitHub cannot send webhook requests to it. Poll SCM allows Jenkins to check the repository by itself.

Polling Schedule — H/5 * * * *: Jenkins checks the repository approximately every 5 minutes. If it detects a new change, the Freestyle job starts and executes build.sh
