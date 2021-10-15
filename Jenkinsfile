pipeline {
    agent {
        label 'worker'
    }
        tools {
            gradle 'gradle4'
        }
        stages {
            stage('checkout') {
                steps {
                checkout scm
                }
            }
            stage('build') {
                steps {
                sh "gradle build"
                }
            }
        }    
        post('post') {
                success {
                   addBadge(icon: completed.gif, text: "Success")
                }
                failure {
                   addBadge(icon: error.gif, text: "Error")    
                }
        
    }    
}
