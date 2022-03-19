pipeline{
    agent any
    stages{
        stage("Sonar Quality Check"){
            stage("docker build & docker push"){
            steps{
                script{
                    withCredentials([string(credentialsId: 'docker_pass', variable: 'docker_password')]) {
                             sh '''
                                docker build -t 34.125.70.200:8083/springapp:${VERSION} .
                                docker login -u admin -p $docker_password 34.125.70.200:8083 
                                docker push  34.125.70.200:8083/springapp:${VERSION}
                                docker rmi 34.125.70.200:8083/springapp:${VERSION}
                             '''
                            }
                    }
                }
            }
        }   
    }   
}
   

