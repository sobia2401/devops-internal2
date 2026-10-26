pipeline{
    agent any
        stages{
            steps{
                stage('Build Docker application'){
                    echo "building docker application"
                    bat 'docker build -t mypythonflaskapp .'
                }
            }
            stage('Run Docker application'){
                echo "running docker application"
                bat 'docker run -f mycontainer|| exit 0'
                bat 'docker run -d -p 5000:5000 --name mycontainer mypythonflaskapp'
            }
        }
        post{
            success{
                echo "pipeline successful"
            }
            fail{
                echo "Pipeline failed. Please check logs"
            }
        }
}