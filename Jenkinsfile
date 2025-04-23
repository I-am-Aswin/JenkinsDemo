pipeline {
    agent any

    stages {
        stage( "compile ") {
            sh "mvn compile"
        }

        stage ("test") {
            sh "mvn test"
        }

        stage( "build" ) {
            sh "mvn clean package"
        }
    }

    post {
        copy(file:"target/JenkinsDemo-0.0.1-SNAPSHOT.jar", tofile:"App.jar")
    }
}