pipeline {
    agent {
        label 'lab01'
    }

    stages {
        stage('Install and Setup Apache') {
            steps {
                sh '''
                sudo apt-get update -y
                sudo apt-get install apache2 unzip wget -y
                wget https://www.free-css.com/assets/files/free-css-templates/download/page296/inance.zip
                sudo unzip inance.zip -d /var/www/html/
                sudo cp -r /var/www/html/inance-html/* /var/www/html/
                sudo systemctl start apache2
                sudo systemctl enable apache2
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh 'touch file_1.txt'
            }
        }

        stage('Production Files') {
            steps {
                sh 'touch file_1{1..5}.txt'
            }
    }
}
