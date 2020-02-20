pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                 bat 'mvn clean compile'
            }
        }

        stage ('Testing Stage') {

            steps {
                 bat 'mvn test'
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    bat 'mvn deploy'
                }
            }
        }
    }
}
