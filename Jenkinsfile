pipeline {
    agent any
    environment {
        name = "naveen singh"
    }
    parameters {
        string(name: 'person', defaultValue: 'Bony Singh', description: "Who are you?")
        booleanParam(name: 'IsMale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Delhi', 'Gurgaon','Noida','Pune' ], description: "")
    }

    stages {
        stage('Run A Command') {
            steps {
                sh '''
                ls
                date
                pwd
                cal 2022
                '''
            }
        }
        stage('Environment Variables') {
            environment {
                username = "naveen kumar"
            }
            steps {
                sh 'echo ${name}'
                sh 'echo ${username}'
            }
        }
        stage('Parameters') {
            steps {
                sh 'echo ${username}'
                sh 'echo ${name}'
                sh 'echo ${person}'
                sh 'echo ${City}'
                echo 'this is a deployment on tomcat'
            }
        }
        stage('Deploy On Tomcat') {
            steps {
                sh 'echo ${username}'
                sh 'echo ${name}'
                echo 'this is a deployment on tomcat'
            }
        }
        stage('Continue ?') {
            input {
                message "Should we continue..?"
                ok "Yes we can..!"
            }
            steps {
                echo "deploy on production server"
            }
        }
        stage('Deploy On Production-Tomcat') {
            steps {
                sh 'echo ${username}'
                sh 'echo ${name}'
                echo 'this is a deployment on tomcat'
            }
        }
    }
    
    post {
        always {
            echo "I will always say Hello again"
        }
        failure {
            echo "Failure"
        }
        success {
            echo "Success"
        }
    }
}
