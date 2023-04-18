pipeline {
    agent { label 'docker'}
    triggers { pollSCM('* 23 * * 1-5') }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/comingapril/StudentCoursesRestAPI.git',
                    branch: 'sprint_1_release' 
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