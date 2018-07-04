pipeline {
    agent {
        node {
            label 'master'
        }
    }
    
    stages {
    
        stage('terraform started') {
            steps {
                sh 'echo "started....!" '
            }
        }
        stage('git clone') {
            steps {
                sh 'sudo rm -r *;sudo git clone https://https://github.com/reddy2018/Practice.git'
            }
        }
        stage('tfsvars create'){
            steps {
                sh 'sudo cp /home/ec2-user/vars.tf ./jenkins/'
            }
        }
        
        stage('terraform init') {
            steps {
                sh 'sudo /home/ec2-user/terraform.init ./jenkins'
            }
        }
        stage('terraform plan') {
            steps {
                sh 'ls ./jenkins; sudo /home/ec2-user/terraform plan ./jenkins'
            }
        }
        stage('terraform ended') {
            steps {
                sh 'echo "Ended......!!"'
            }
        }
        
   }
}
