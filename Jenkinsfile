node{
    def MavenHome=tool name:"MavenHome",type:"maven"
    stage("check out from git"){
        git credentialsId: '2b6634a3-3db1-49ea-be5c-06d10a9bd6d7', url: 'https://github.com/srujanakumari/maven-web-application.git'
    }
    stage("build"){
        sh "${MavenHome}/bin/mvn clean package"
        
    }
//     stage("deploy to tomcat"){
//         sshagent(['94c6ef15-5b66-4bab-91e6-e0cfa8d86298']) {
//     sh "scp -o StrictHostKeyChecking=no ${WORKSPACE}/target/*.war ec2-user@172.31.0.176:/opt/apache-tomcat-8.5.47/webapps"
// }
        
//     }
stage("deploy"){
    sshagent(['e9514da3-59d9-4049-a70d-30096b9d71ec']) {
    sh " scp -o StrictHostKeyChecking=no ${WORKSPACE}/target/*.war ec2-user@13.127.92.27:/opt/apache-tomcat-8.5.47/webapps"
}
}
}
