pipeline {
    agent { label 'docker'}
    triggers { pollSCM('* * * * *') }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/comingapril/StudentCoursesRestAPI.git',
                    branch: 'develop' 
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t tnaveen/spc:latest .'
            }
        }
        stage('scan and push ') {
            steps {
                sh 'echo docker scan tnaveen/spc:latest'
                sh 'docker image push tnaveen/spc:latest'
            }
        }
    }
}