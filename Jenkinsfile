pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'git version'
                sh 'ls'
                sh 'azcopy cp "/var/lib/jenkins/workspace/copy-to-blob-storage-pipeline/" "https://allansteststorage.blob.core.windows.net/testjenkins?sv=2019-10-10&ss=bfqt&srt=sco&sp=rwdlacupx&se=2020-06-15T00:13:00Z&st=2020-06-12T16:13:00Z&spr=https&sig=zbJAzkLJnP7gsn%2BPKnJdiq%2BqUufiWLpxyw9%2Brmq3bbA%3D" --recursive=true'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                echo '/usr/local/bin/kubectl  apply -f nginx.yaml'
            }
        }
    }
}
