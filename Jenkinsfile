pipeline{
    agent any
    tools{maven 'M3'}
 stages{
    stage('Checkout'){
        steps{
            git branch: 'main', url:'https://github.com/francois-90/SpringPetClinic.git'
        }
    }
    stage ('Build'){
        steps{
        withMaven(maven: 'M3'){
            sh 'mvn compile'
            }
        }
    }
    stage ('Test'){
        steps{
            sh 'mvn test'
        }
    }
    stage ('Package'){
        steps{
            sh 'mvn package'
        }
    }
    stage ('Deploy'){
        steps{
            sh 'java -jar /home/coder/.jenkins/workspace/MyDeclarativePipeline/target/*.jar'
        }
    }
    }
}
