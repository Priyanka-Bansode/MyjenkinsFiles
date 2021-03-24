node('nodes')
{
    
    def mavenHome = tool name: "maven3.6.3"
    
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
    
    stage('CheckoutCode')
    {
        git branch: 'development', credentialsId: '13ac94c4-fb50-4c81-b28a-b2665fa5ccc0', url: 'https://github.com/Priyanka-Bansode/maven-web-application.git'
    }
    
    stage('build')
    {
        sh "${mavenHome}/bin/mvn clean package"
    }
    /*
    stage('ExcuteSonarQubeReport')
    {
        sh "${mavenHome}/bin/mvn sonar:sonar"
    }
    
    stage('UploadArtifactintoNexus')
    {
        sh "${mavenHome}/bin/mvn deploy"
    }
    
    stage('DeployAppIntoTomcatServer')
    {
        sshagent(['23738182-c2c3-4b4c-a140-5bc473bd3cce'])
        {
            sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@65.0.105.188:/opt/apache-tomcat-9.0.44/webapps/"
        }

    }
    
    stage('SendEmailNotification')
    {
        emailext body: '''deploy complete

Regards
Priyanka''', subject: 'Build Over', to: 'priyanka.vhansure@gmail.com'
    }
    */
}
