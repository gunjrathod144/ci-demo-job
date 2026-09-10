Bugs found

       1. stage('Checkout') is outside stages {} — all stages must be inside the stages block. 
       
       2. stages {} is placed inside the Checkout stage — it should be at the top level, directly inside pipeline {}. 
       
       3.  Missing } after Checkout — the Checkout stage is not closed before stages {} starts. 
       
       4.  Missing { after stage('Unit Tests') — it should be stage('Unit Tests') {. 
       
       5. parallel block structure is broken — both Unit Tests and Lint must be complete stage blocks inside parallel {}. 
       
       6. Cleanup command is logically incorrect — rm -rf workspace/* targets a workspace subdirectory rather than the Jenkins workspace; use deleteDir(). 
