pipeline {
        agent any
        stages {
            stage('Build') {
                steps {
                    sh 'rsync -av -e "ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/firstEc2.pem" /var/lib/jenkins/workspace/chatappPipeline/ ubuntu@10.0.2.128:/home/ubuntu/new_chatapp'
                }
            }

           
            stage('Deploy') {
                steps {
                    sh 'ssh -i /var/lib/jenkins/firstEc2.pem ubuntu@10.0.2.128 sudo systemctl restart gunicorn'
                }
            }
        }
    }
