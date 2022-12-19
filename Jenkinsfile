pipeline{
    agent any
    tools {
        maven 'maven_3_8_6'
    }
    stages{
       stage('GetCode'){
            steps{
                git 'https://github.com/Alfinshaji13/sonarqube.git'
            }
         }        
       stage('Build'){
            steps{
                bat 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.7.0';
        steps{
        withSonarQubeEnv('sonarqube-8.9') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        bat "mvn sonar:sonar"
    }
        }
        }
       
    }
}
