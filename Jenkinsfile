pipeline{
    agent any
    stages{
        (1-clone){
            steps{
                sh 'cat/etc/passwd'
            }
        }
        stage(2-parallel jobs){
            parallel{
                stage('1-sub job1'){
                    steps{
                        sh 'lscpu'
                    }
                }
            }
            stage('subjob2'){
                steps{
                    sh 'df -h'
                }
            }
        }
        stage('3-codetest'){
            steps{
                sh 'free -m'
            }
        }
        stage('4-closing'){
            steps{
                echo "thank you for a good job"
            }
        }
    }
}