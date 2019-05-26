node('master'){
    
stage('Checkout') {
    git 'https://github.com/monika-punia/JenkinsTest.git'
}

stage('Compile'){
bat label: '', script: 'mvn clean package'
}
stage('Archiving Files'){
archiveArtifacts 'target/*.jar'
}
step([$class: 'JUnitResultArchiver', testResults: 'target\\surefire-reports\\TEST-*.xml'])
}
