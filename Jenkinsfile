pipeline {
    agent any

    tools {
        
        maven "M3"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', url: 'https://github.com/KavyaKanupuru/JenkinsTest2.git'

                // Run Maven on a Unix agent.
                sh "mvn -Dmaven.test.failure.ignore=true package"
                
                sh "echo 'first proj is built'"
                
                git branch: 'main', url: 'https://github.com/KavyaKanupuru/JenkinsTest1.git'

                sh "mvn -Dmaven.test.failure.ignore=true package"
                
                 sh "echo '2nd proj built'"
            }
            
        }
    }
}
