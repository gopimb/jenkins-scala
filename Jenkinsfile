pipeline {
    agent any

    stages {        
                def sbtHome = tool 'sbt-0.13.15'
  def sbt = "${sbtHome}/bin/sbt -no-colors -batch"
  stage('build') {
    sh "${sbt} clean compile"
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh "sbt run"
            }
        }

        stage('Package') {
            steps {
                echo "Packaging..."
                sh "sbt test"
            }
        }

    }
}

