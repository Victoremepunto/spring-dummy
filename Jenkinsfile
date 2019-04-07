
pipeline {
    
    agent any

    stages {
        
        stage('Init') {
            steps {
                git 'https://github.com/Victoremepunto/spring-dummy.git'
            }
        }
        
        stage('Example Build and Test') {

            steps {
                sh './gradlew clean test jacocoTestReport'
                publishCoverage adapters: [jacocoAdapter('build/reports/jacoco/test/jacocoTestReport.xml')], sourceFileResolver: sourceFiles('NEVER_STORE')
            }
        }
    }
}
