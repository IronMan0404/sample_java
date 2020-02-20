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
        stage('JacocoPublisher') {
        // junit '*/build/test-results/*.xml'
            step([$class: 'JacocoPublisher', 
                execPattern: 'target/*.exec',
                classPattern: 'target/classes',
                sourcePattern: 'src/main/java',
                exclusionPattern: 'src/test*'
])
     
}


        stage ('Deployment Stage') {
            steps {
                 bat 'mvn deploy'
            }
        }
    }
}
