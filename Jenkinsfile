pipeline {
    agent { label 'Ubuntu-16-Docker' }

    stages {
        stage('Install maven') {
            steps {
                echo $(pwd)
                sh 'curl -sSL https://www-us.apache.org/dist/maven/maven-3/3.6.1/binaries/apache-maven-3.6.1-bin.tar.gz | tar xzv'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                sh "/home/ec2-user/apache-maven-3.6.1/bin/mvn compile"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh '/home/ec2-user/apache-maven-3.6.1/bin/mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh '/home/ec2-user/apache-maven-3.6.1/bin/mvn install'
            }
        }
    }
}
