node('slave1') { //optionally add node label: node (‘slave1’)
 gradle4 = tool 'gradle4'
 try {
  stage ('checkout'){
     checkout scm
  }
  stage ('build')
  {
      sh "${gradle4}/bin/gradle build"
  }
 } catch (ex) {
  echo 'Error occured'
 }
 stage('post') {
  if ( currentBuild.result == 'SUCCESS') {
   addBadge(icon: 'green.gif', text: 'Build Succeeded')
  }
  if (currentBuild.result == 'FAILURE') {
   addBadge(icon: 'red.gif', text: 'Build Failed')
  } 
 }
}
