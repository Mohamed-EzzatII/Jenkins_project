pipline{
    agent any
    stages{
        
        stage("Clean up"){
            steps{
                deleteDir()
            }
        }

        stage("Clone Repo"){
            steps{
                sh "git clone https://github.com/Mohamed-EzzatII/Jenkins_project.git"
            }
        }

        stage("Create Namespace"){
            steps{
                sh "cd Jenkins_project"
                sh "kubectl create namespace devops-tools"
                sh "kubectl apply -f serviceAccount.yaml"
                sh "kubectl apply -f volume.yaml"
                sh "kubectl apply -f deployment.yaml"
                sh "kubectl get deployments -n devops-tools"
                sh "kubectl apply -f service.yaml"
            }
        }

    }
}