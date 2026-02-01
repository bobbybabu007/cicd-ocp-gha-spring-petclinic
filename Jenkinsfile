pipeline {
    agent {
        label "java"
    }
    stages {
        stage('SCM') {
            steps {
                echo 'Cloning the Code Repository..'
                git branch: 'main', url: 'https://github.com/bobbybabu007/cicd-ocp-gha-spring-petclinic.git'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging....'
                sh 'mvn package'
            }
        }
                stage('Archiving') {
            steps {
                echo 'Archiving JAR File....'
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
    }
}
