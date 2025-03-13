pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/mschandana16/PES1UG22CS314_Jenkins'
        FILE_NAME = 'PES1UG22CS314-1.cpp'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    sh '''
                    g++ -o PES1UG22CS314-1 PES1UG22CS314-1.cpp
                    echo "Build successful"
                    '''
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh '''
                    ./PES1UG22CS314-1
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh '''
                    git config --global user.email "chandanasuresh2004@gmail.com"
                    git config --global user.name "mschandana16"
                    git clone $REPO_URL repo
                    cd repo
                    echo '// Sample C++ file' > $FILE_NAME
                    git add $FILE_NAME
                    git commit -m "Added $FILE_NAME"
                    git push
                    '''
                }
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed"
        }
    }
}
