pipeline {
    agent { label 'java-docker-slave' }
    
    stages {
       stage('checkout') {
         steps {
         
checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'cheeti-github',url: 'https://github.com/cheetisrinivas/simple-java-maven-app.git']]]
        }        
}

        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
   }
   
}

