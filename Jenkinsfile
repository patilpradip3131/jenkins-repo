pipeline {
    agent {
        label {
            label "slave-1"   
            
        }
        
    }
      

    stages {
        stage ('Compile Stage') {

            steps {
                    sh 'sudo yum install maven -y'
                    sh 'sudo mvn clean compile'
                }
            
        }

        stage ('Testing Stage') {

            steps {
                
                    sh 'sudo mvn test'
                }
            
        }


        stage ('Install Stage') {
            steps {
                
                    sh 'sudo mvn install'
                }
            
        }
        
        stage ('Echo Branch') {

            steps {
                
                    echo "This is master branch"
                }
            
        }
        
          stage ('deploy') {

            steps {
                 
                dir ("/mnt/server") {
                sh "sudo cp -r /mnt/jenkins-slave/workspace/jenkins-repo_master/target/jenkins-example-1.0-SNAPSHOT.jar /mnt/server/apache-tomcat-9.0.73/webapps"
                sh "sudo ./startup.sh"     
                }
                
                
                   
                }
            
        }
    }
}
