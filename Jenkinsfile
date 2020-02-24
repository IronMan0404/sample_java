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


        stage ('Deployment Stage') {
            steps {
                 bat 'mvn deploy'
            }
        }
//        stage('SonarQube analysis') {
//            def scannerHome = tool 'SonarScanner 4.0';
//            withSonarQubeEnv('My SonarQube Server') { // If you have configured more than one global server connection, you can specify its name
//                sh "${scannerHome}/bin/sonar-scanner"
//    }
//  }

//        stage("Quality Gate") {
 //           steps {
 //               timeout(time: 1, unit: 'HOURS') {
                    // Parameter indicates whether to set pipeline to UNSTABLE if Quality Gate fails
                    // true = set pipeline to UNSTABLE, false = don't
 //                   waitForQualityGate abortPipeline: true
   //             }
     //       }
    }
}
