pipeline {
  agent any

  stages {
    stage('Clone') {
      steps {
        echo 'Cloning repo...'
        git 'https://github.com/anth63/jenkins-html-demo.git'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying index.html to Apache server...'
        sh '''
        scp -o StrictHostKeyChecking=no -i /home/ubuntu/your-key.pem index.html ubuntu@<EC2_PUBLIC_IP>:/var/www/html/
        '''
      }
    }
  }
}
