pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("Depoy"){
            steps{
                deploy adapters: [
                    tomcat7(
                        credentialsId: 'db30f74b-3751-44ba-b5ff-5529cf21f59d',
                        path: '',
                        url: 'http://ec2-15-237-56-246.eu-west-3.compute.amazonaws.com:8080/')
                    ],
                    contextPath: 'javawebapp2',
                    war: 'target/*.war'
            }
        }
    }
}


















