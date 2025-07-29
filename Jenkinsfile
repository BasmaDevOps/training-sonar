pipeline {
    agent any
    stages {
        //Continuous Integration
        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('SonarQube'){
            steps{
                sh "mvn clean verify sonar:sonar \
                    -Dsonar.projectKey=compare-app \
                    -Dsonar.host.url=http://35.180.225.248:9000 \
                    -Dsonar.login=sqp_bef15ac51e7a97c31a7e45980ff3c30b6647b4c3"
            }
        }
    }
}
