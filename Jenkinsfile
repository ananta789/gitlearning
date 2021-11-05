pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('sourcecodemanagement stage') {
            steps {
                echo 'BATCH3 DEVOPS CHAMPS'
                git 'https://github.com/wakaleo/game-of-life.git'
            }
        }
        stage('ARTIFAT BUILD STAGE') {
            steps {
                echo 'BUILDING WITH MAVEN TOOL'
                sh 'mvn clean install'
            }
        }
        stage('DEPLOY TO TOMCAT STAGE') {
            steps {
                echo 'DEPLOYING INTOMCAT'
              deploy adapters: [tomcat9(credentialsId: 'e0259c9f-d114-48d9-b32d-aefcec81d2a6', path: '', url: 'http://3.21.159.166:8080/')], contextPath: null, war: '**/*.war'  
            }
        }
    }
}
