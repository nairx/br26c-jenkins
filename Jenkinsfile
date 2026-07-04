pipeline {

    agent any

    tools {
        jdk 'JDK21'
        maven 'Maven3'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/nairx/br26c-jenkins.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                bat 'copy target\\br26c-jenkins-1.0.jar D:\\hello-world\\hello.jar'
            }
        }

        stage('Run Application') {
            steps {
                bat '''
                taskkill /F /IM java.exe || exit 0
                start java -jar D:\\hello-world\\hello.jar
                '''
            }
        }

    }

}


// pipeline {
//     agent any

//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building application...'
//             }
//         }

//         stage('Test') {
//             steps {
//                 echo 'Running tests...'
//             }
//         }

//         stage('Deploy') {
//             steps {
//                 echo 'Deploying application...'
//             }
//         }
//     }
// }
