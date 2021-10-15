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
                sh "gradle clean build clean"
                }
            }
            stage('unit-test') {
                steps {
                sh "gradle test"
                junit "build/test-result/junit-platform/*.xml"
                }
            }
       
            stage('func-test') {
                steps('step1') {
                sh "test-data/int-test.sh build/libs/oto-gradle-1.0.jar otoMato 'Hello Otomato!'"
                }
                steps('step2') {
                sh "test-data/int-test.sh build/libs/oto-gradle-1.0.jar otoMato '... ...'"
                }
                steps('step3') {
                sh "test-data/int-test.sh build/libs/oto-gradle-1.0.jar otoMato 'just another text!'"    
        
         }       
        }    
        post('post') {
                success {
                   addBadge(icon: "completed.gif", text: "Success")
                }
                failure {
                   addBadge(icon: "error.gif", text: "Error")    
                }
        
    }    
 }
}
