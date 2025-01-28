pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo "docker build"
                    if (env.GIT_BRANCH == 'origin/dev') {
                        sh 'docker build -t danushvithiyarth/dev:latest .'
                    } else if (env.GIT_BRANCH == 'origin/main') {
                        sh 'docker build -t danushvithiyarth/prod:latest .'
                    }
                }
            }
        }
        stage('Push') {
            steps {
                script {
                    sh 'docker login -u "danushvithiyarth" -p "$Docker_pass" docker.io'
                    if (env.GIT_BRANCH == 'origin/dev') {
                        sh 'docker push danushvithiyarth/dev:latest'
                    } else if (env.GIT_BRANCH == 'origin/main') {
                        sh 'docker push danushvithiyarth/prod:latest'
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh 'docker rm -f $(docker ps -aq)'
                    if (env.GIT_BRANCH == 'origin/dev') {
                        sh 'docker run -d -p 800:80 danushvithiyarth/dev:latest'
                    } else if (env.GIT_BRANCH == 'origin/main') {
                        sh 'docker run -d -p 80:80 danushvithiyarth/prod:latest'
                    }
                }
            }
        }
        stage('Cleanup') {
            steps {
                script {
                    sh 'docker image prune -f'
                }
            }
        }
    }
}
