pipeline
{
  agent any
  options
    {
        buildDiscarder(logRotator(numToKeepStr: '5', artifactNumToKeepStr: '5'))
    }
  tools
    {
        maven 'maven_3.9.4'
//sonarqubeScanner 'sonarqubeScanner'
    }
  stages
  {
    stage('code compilation')
    {
       steps
    {
        echo 'code compilation is in progress'
        sh 'mvn clean compile'
        echo 'code compilation is completed successfully!'
    }
  }
    stage('code QA Execution')
    {

        steps
        {
            echo 'JUnit Test Case Check in progress'
            sh 'mvn clean test'
            echo 'JUnit Test Case Check completed successfully!'
        }
    }
    stage('code package')
        {

              steps
              {
                 echo 'Creating WAR Artifact'
                 sh 'mvn clean package'
                 echo 'Artifact Creation completed successfully!'
              }
        }
    }
  }