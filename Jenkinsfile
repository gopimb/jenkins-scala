pipeline {
    agent any
 stages {       
         stage('Compile') {
             steps{
                         sh "${tool name: '', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt compile"

             }
      }

        stage('Run') {
            steps {
                echo "Running..."
                sh "${tool name: '', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt run"

            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh "${tool name: '', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt test"

            }
        }

        stage('Package'){
            steps{
               echo "Packaging..."
               sh "${tool name: '', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt package"


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

