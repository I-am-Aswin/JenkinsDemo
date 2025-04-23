pipeline {
    agent any

    stages {
        stage( "compile ") {
            steps {
                sh "mvn compile"
            }
        }

        stage ("test") {
            steps{
                sh "mvn test"
            }
        }

        stage( "build" ) {
            steps {
                sh "mvn clean package"
            }
        }
    }

    post {
        copy(file:"target/JenkinsDemo-0.0.1-SNAPSHOT.jar", tofile:"App.jar")
    }
}