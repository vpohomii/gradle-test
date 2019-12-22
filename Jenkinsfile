node { //optionally add node label: node (‘slave1’)
 gradle4 = tool 'gradle4'
 stage ('checkout'){
    checkout scm
 }
 stage ('build')
 {
     sh "${gradle4}/bin/gradle build"
 }
}
