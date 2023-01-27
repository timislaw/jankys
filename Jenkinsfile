/* Requires the Docker Pipeline plugin */
// pipeline {
//     agent { docker { image 'python:3.10.7-alpine' } }
//     stages {
//         stage('build') {
//             steps {
//                 sh 'python --version'
//             }
//         }
//     }
// }


// pipeline {
//     agent any
//     stages {
//         stage('Build') {
//             steps {
//                 sh 'echo "Hello World"'
//                 sh '''
//                     echo "Multiline shell steps works too"
//                     ls -lah
//                 '''
//             }
//         }
//     }
// }

// pipeline {
//     agent any
//     stages {
//         stage('Deploy') {
//             steps {
//                 retry(3) {
//                     sh './flakey-deploy.sh'
//                 }

//                 timeout(time: 3, unit: 'MINUTES') {
//                     sh './health-check.sh'
//                 }
//             }
//         }
//     }
// }


pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                timeout(time: 3, unit: 'MINUTES') {
                    retry(5) {
                        sh './flakey-deploy.sh'
                    }
                }
            }
        }
    }
}