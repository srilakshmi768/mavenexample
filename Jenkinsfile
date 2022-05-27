node('java_3.8.5') {
    properties([pipelineTriggers([upstream('demoProject, ')])])
   stage('git') {
    git branch: 'scripted', credentialsId: 'MAVEN-BUILDS', url: 'https://github.com/srilakshmi768/mavenexample.git'
}
stage('build'){
    sh '''
    echo 'PATH=${PATH}'
    echo 'M2_HOME=${M2_HOME}'
    '''
    sh '/usr/local/apache-maven-3.8.5/bin/mvn clean package'
}
stage('testing'){
    junit '**/TEST-*.xml'
}
stage('archive'){
    archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
}
}