pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                sh "mvn clean install"
            }
        }
        stage('deploy'){
            steps{
                deploy adapters: [tomcat8(credentialsId: '2491c258-9cde-4bf4-bb76-5d136e251ced', path: '',
                url: 'http://ec2-65-0-86-236.ap-south-1.compute.amazonaws.com:8080/')],
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
