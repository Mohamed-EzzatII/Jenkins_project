pipeline{
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
                sh "cd /var/lib/jenkins/workspace/jenkins_project/Jenkins_project/jenkins_yaml"
                sh "sudo kubectl create namespace devops-tools"
                sh "sudo kubectl apply -f serviceAccount.yaml"
                sh "sudo kubectl apply -f volume.yaml"
                sh "sudo kubectl apply -f deployment.yaml"
                sh "sudo kubectl get deployments -n devops-tools"
                sh "sudo kubectl apply -f service.yaml"
                sh "cd .."
                sh "./start.sh"
            }
        }

    }
}