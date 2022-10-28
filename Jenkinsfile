pipeline{
    agent none
    stages{
        stage('Non-Parallel Stage'){
            agent any
            steps{
                echo 'This stage will be exceuted first'
            }
        }

        stage('Run Tests'){
            parallel{
                stage('Test On Windows'){
                    agent{
                        label 'windows-agent'
                    }
                    steps{
                        echo 'Task 1 on Agent'
                    }
                }
                stage('Test on Master'){
                    agent any
                    steps{
                        echo "Task 1 on Master"
                    }
                }

            }
        }
    }
}