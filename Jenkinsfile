pipeline {
    agent any

    stages {
        stage('Install Apache2') {
            steps {
                sshagent(['a1bd5209-27dd-4176-abd4-f04f553ef3f9']) {
                    sh '''
                    ssh -o StrictHostKeyChecking=no jenkins@192.168.1.45 <<EOF
                        echo "UPDATE UBUNTU"
                        sudo apt-get update -y
                        
                        echo "INSTALL APACHE2"
                        sudo apt-get install -y apache2
                        
                        echo "AUTOSTART APACHE2"
                        sudo systemctl enable apache2
                        
                        echo "START APACHE2"
                        sudo systemctl start apache2
EOF
                    '''
                }
            }
        }
    }
}
