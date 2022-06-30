pipeline {
    agent {
        label "master"
    }
    tools {
     maven 'maven'
    }
    environment {
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "https"
        NEXUS_URL = "nexus-lab.pp.ua"
        NEXUS_REPOSITORY = "maven-lab"
        NEXUS_CREDENTIAL_ID = "nexus-user-credentials"
    }
   stages {
     stage("Clone code from GIT") {
        steps {
          script {
            git branch: 'main', 
                url: 'https://github.com/atrofymchuk/spring-petclinic.git'
                    
          }
        }
     }
     stage('Download artifact Nexus Repository Manager') {
       steps {
         sh 'mvn dependency:get -DgroupId=org.springframework.samples -DartifactId=spring-petclinic -Dversion=2.7.0 -Dpackaging=jar -Dclassifier=sources -DremoteRepositories=https://nexus-lab.pp.ua/maven2'
       }
     }
     
   }
}
