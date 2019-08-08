pipeline {
    agent any

    stages {
        stage('Install maven') {
            steps {
                echo $(pwd)
                curl -sSL https://www-us.apache.org/dist/maven/maven-3/3.6.1/binaries/apache-maven-3.6.1-bin.tar.gz | tar xzv
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                /home/ec2-user/apache-maven-3.6.1/bin/mvn compile
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                /home/ec2-user/apache-maven-3.6.1/bin/mvn test
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                /home/ec2-user/apache-maven-3.6.1/bin/mvn install
            }
        }
    }
}
