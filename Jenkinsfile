pipeline {
  agent any {
    tools {
      maven:'Maven'
      jdk:'JDK21'
    }
  }
    stages {
      stage('Checkout') {
        steps {
          git branch :'main',url:'https://github.com/KeerthanaAR123/MavenLab.git',
            credentialsID:'github-token'
        }
      }
      stage('Test') {
        steps {
          sh 'mvn test'
        }
      }
      stage('Package') {
        steps {
          sh 'mn package'
        }
      }
      stage('Run Application') {
        steps {
          sh 'mvn exec:java -Dexec.mainClass="com.example.app.App"'
        }
      }
    }
}
