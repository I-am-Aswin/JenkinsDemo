pipeline {
    agent { docker { image 'maven:3.8.6-jdk-11' } }

    stages {
        stage("compile") {
            steps {
                echo "Compiling the Application for errors"
                sh "mvn compile"
            }
        }

        stage("test") {
            steps{
                echo "Running Test Scripts of the Application"
                sh "mvn test"
            }
        }

        stage( "build" ) {
            steps {
                echo "Building and Bundling the Application"
                sh "mvn clean package"
            }
        }
    }

    post {
        success {
            echo "Package Built Successfully"
            sh "cp target/JenkinsDemo-0.0.1-SNAPSHOT.jar app.jar"
        }
        failure {
            echo "Error Building Application"
        }
    }
}
