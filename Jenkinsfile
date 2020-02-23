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
            steps {
                step([$class: 'JacocoPublisher', 
                    execPattern: 'target/*.exec',
                    classPattern: 'target/classes',
                    sourcePattern: 'src/main/java',
                    exclusionPattern: 'src/test/java/works/buddy/samples/*'
])
            }
}


        //stage ('Deployment Stage') {
         //   steps {
                 //bat 'mvn deploy'
           // }
        //}
    }
}
