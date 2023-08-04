pipeline {
         agent any
         tools {
                  maven "Maven"
                  jdk "JDK11"
         }
         stages {
                  stage('Initialize'){
                           steps{
                                    echo "PATH = ${M2_HOME}/bin:${PATH}"
                echo "M2_HOME = /opt/maven"
            }
        }
                  stage('Validate'){
                         steps{
                           echo "VALIDATE"
                           bat "mvn validate"
                         }
                  }        
               stage('Compile'){
            steps{
                echo "COMPILE"
             bat "mvn compile"
            }
        }
       
            stage('SnykScanning') {
                steps {
                    // One or more steps need to be included within the steps block.
                    snykSecurity snykInstallation: 'Snyk',
                    snykTokenId: 'snyk-api-abhijieet'
                }
            }
        

// stage('test'){
// steps{
// echo "Test"
// bat "mvn clean test"
// }
// }
// stage('Sonar Analysis') {
// steps {
// // use the SonarQube Scanner to analyze the project
// withSonarQubeEnv('SonarQube') {
//      bat 'mvn sonar:sonar'
// }
// }
// }
                  
//                       stage('Package'){
//             steps{
//                 echo "PACKAGE"
//              bat "mvn package"
//             }
//         }
                  
//                    stage('Install'){
//             steps{
//                 echo "INSTALL   "
//              bat "mvn clean install"
//             }
//         }
                  
// stage('Upload_Artifact') {
// steps {
//     script{
// def server = Artifactory.server 'artifactory'
//                def uploadSpec = """{
// "files": [
// {
//       "pattern": "target/*.jar",
// "target": "Abhijeet_master/"
// }
// ]
// }"""
// server.upload(uploadSpec)
// }
// }
// }
// }
    
//            post {
//                  always {
//                       jiraSendBuildInfo site: 'abhijeetfirstjirasite.atlassian.net'
//                  }
//              }
         }
}
