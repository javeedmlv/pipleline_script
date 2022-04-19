pipeline {
    agent {
        label 'node1'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..';
                git branch: 'main', credentialsId: 'ad7d050b-b496-4744-92cb-d351fc15d490', url: 'https://github.com/javeedmlv/pipleline_script.git';
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..';
                sh 'sh build.sh'
            }
        }
//         stage('Deploy') {
//             steps {
//                 echo 'Deploying....'
//             }
//         }
        stage('Deploy to Production') {
            when {
                expression { 
                   return params.ENVIRONMENT == 'PROD'
                }
            }
            steps {
                    sh """
                    echo "deploy to production"
                    """
                }
            }
   }
    }
}
