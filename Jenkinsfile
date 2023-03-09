pipeline {
    agent {
        label {
            label "slave-1"   
            
        }
        
    }
      

    stages {
        stage ('Compile Stage') {

            steps {
                    sh 'yum install maven -y'
                    sh 'mvn clean compile'
                }
            
        }

        stage ('Testing Stage') {

            steps {
                
                    sh 'mvn test'
                }
            
        }


        stage ('Install Stage') {
            steps {
                
                    sh 'mvn install'
                }
            
        }
        
        stage ('Echo Branch') {

            steps {
                
                    echo "This is master branch"
                }
            
        }
    }
}
