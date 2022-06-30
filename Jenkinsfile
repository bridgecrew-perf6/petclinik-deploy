pipeline {
   agent any
   stages {
     stage('Download artifact') {
       steps {
         sh 'wget http://localhost:8081/repository/maven-releases/org/springframework/samples/spring-petclinic/2.7.0/spring-petclinic-2.7.0.jar'
       }
     }
     stage('Run app') {
       steps {
         sh 'sudo nohup java -jar ./*.jar &'
       }
     }
   }
}
