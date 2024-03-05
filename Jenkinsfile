pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file using shell script
                    sh 'g++ -o output_file PES1UG21CS054-1.cpp'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Print output of .cpp file using shell script
                    sh './output_file'
                }
            }
        }
        // Add more stages for deployment if needed
    }
    
    post {
        always {
            // Display 'pipeline failed' in case of any errors within the pipeline
            script {
                currentBuild.result = currentBuild.result ?: 'SUCCESS'
                if (currentBuild.result == 'FAILURE') {
                    echo 'Pipeline failed'
                }
            }
        }
    }
}
