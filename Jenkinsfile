pipeline {
    agent any
 stages {       
         stage('Compile') {
             steps{
         sh "/usr/local/bin/sbt compile"
             }
      }

        stage('Run') {
            steps {
                echo "Running..."
                sh "sbt run"
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh "sbt test"
            }
        }

        stage('Package'){
            steps{
               echo "Packaging..."
               sh "sbt package"

            }
        }

        stage('sanity check'){
            steps{
             input("does the project  is ready to deploy ?")

            }
        }

        stage('Build Status'){
            steps{
             echo "Here your pipeline is get successfully executed"

            }
        }

    }
}

