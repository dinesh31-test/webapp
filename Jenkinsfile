pipeline {

agent {
    node {
      label 'master'
    }
  }
  
      tools {
          maven "Maven 3.8.1"
    }
    
    stages {
        
     stage('Maven version') {
            steps {
                echo "Hello, Maven"
                sh "mvn --version" 
            }
        }
      stage('SonarQube Scanner') {
         environment {
            SCANNER_HOME = tool 'SonarQube-4.6.2'
            ORGANIZATION = "maven_pipeline"
            PROJECT_NAME = "maven_pipeline"
          }
  steps {
    withSonarQubeEnv('SonarQube') {
        -Dsonar.java.binaries=build/classes/java/ \
        -Dsonar.projectKey=$PROJECT_NAME \
        -Dsonar.sources=.'''
    }
  }
}
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
            
        }
        
        stage('Stage 2') {
            steps {
                echo 'Stage2 Hello world!'  
                echo  'Stage2 $date'
                echo  'Stage2 $date'
            }
            
        }
        
        
        stage('Stage 3') {
            steps {
                echo 'Wel come to Stage3 '  
                echo  'Stage3 '
            }
            
        }           
    }
}
