pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'git version'
                sh 'ls'
                sh 'azcopy cp "/var/lib/jenkins/workspace/copy-to-blob-storage-pipeline/" "https://allansteststorage.blob.core.windows.net/testjenkins?sv=2019-10-10&ss=bfqt&srt=sco&sp=rwdlacupx&se=2020-06-18T18:38:03Z&st=2020-06-18T10:38:03Z&spr=https&sig=%2BQt%2BebAN6%2FxAgcp%2BDOOz4kf1nQTaJeroBjXGl4hQe4E%3D" --recursive=true'
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
