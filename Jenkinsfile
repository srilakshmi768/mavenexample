

pipeline{
    agent {label 'java_3.8.5'}
    triggers { upstream(upstreamProjects: 'demoProject', threshold: hudson.model.Result.SUCCESS) }
    stages{
        stage('git'){
            steps{
            git url:'https://github.com/srilakshmi768/mavenexample.git'
        }
    }
    stage('build'){
        sh '/usr/local/apache-maven-3.8.5/bin/mvn clean package'
    }
}
}