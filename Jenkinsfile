pipeline {
    agent { label 'terraform'}
    stages{
        stage('CI'){
            steps{
                echo "FRONTEND_CI"
            }
        }
        stage('code quality checks'){
            steps{
                echo "code qiality checks using sonar qube"
                sh 'sonar-scanner -Dsonar.projectkey=frontend -Dsonar.host.url=http://172.31.17.88:9000 -Dsonar.login=admin -Dsonar.password=harsha123 -Dsonar.qualitygate.wait=true'
            }
        }
        stage('code deploy'){
            input{
                message "should be continue?"
            }
            steps{
                echo "code release"
            }
        }
    }
}