pipeline{
    agent any
    stages{
        stage('Git project fetch') {
            steps{
                git poll: false, url: 'https://github.com/michalgorowij/junit4.git'
            }
        }
        stage('Build project') {
            steps{
                withMaven(jdk: 'JAVA8', maven: 'Maven', tempBinDir: '') {
                    sh "mvn clean verify" // some block
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }
    }
}