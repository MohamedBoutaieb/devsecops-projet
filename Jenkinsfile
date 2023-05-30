pipeline {
    agent any 
    stages { 
        //all the stages for example the test stage or build stage and dockerize stage and deploy stage
        stage("testing the fetch of reposittory") {
            steps{
                echo "I am building the app"
            }
        }
        stage("building the docker images") {
            steps{
                echo "I am testing the app"
                withCredentials([usernamePassword(credentialsId: 'docker-hub', passwordVariable: 'PASS' , usernameVariable: 'USER')]){
                    sh 'docker  build -t slim637/devsecops-project:v-1.0 .'
                    sh "echo $PASS | docker login -u $USER --password-stdin "
                    sh 'docker push slim637/devsecops-project:v-1.0'
                }
            }
        }
        stage("code quality test") {
            steps{
                echo "I am testing the quality of the code"
            }
        }
        stage("deploy") {
            steps{
                echo "I am deploying the app"
                
            }
        }

}}  