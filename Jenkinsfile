node{ 
 stage('Pull Git Repo') {
   git 'https://github.com/amitvashist7/jenkins-devops-062019.git'
}
   def project_path = "atmosphere/spring-boot-samples/spring-boot-sample-atmosphere/"
 
   dir(project_path) { 
   stage('Clean old Packages') {       
   sh label: '', script: 'mvn clean'
   }
   
   stage('Build Package') {
   sh label: '', script: 'mvn package'
   }
   
   stage('Code Quality') {
   sh label: '', script: 'mvn verify'
   }
   
 stage('Parallel Jobs') 
 parallel "Code Quality Publish":{
   publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/site/jacoco/', reportFiles: 'index.html', reportName: 'Jococo Code Quality Report', reportTitles: 'Code Quality Report'])
   },
  "Test Results Publish": {
   junit 'target/surefire-reports/TEST-*.xml'
   }
   
   
   stage('Archive Artifacts') {
   archive 'target/*.jar'
   }
   
 
   
   }
    
}
