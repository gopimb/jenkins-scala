pipeline {
    agent any
 stages {       
         stage('Compile') {
             steps{
                         sh "sbt compile"

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
        stage('Run') {
            steps {
                echo "Running..."
                sh "sbt run"
            }
        }
     stage('Build status') {
            steps {
                githubNotify account: 'sakshigawande12', context: 'build-status', credentialsId: '5f3f4be6-94a3-4991-8515-d8936cc4f147', description: 'passed', gitApiUrl: '', repo: 'HelloWorld', sha: "${GIT_COMMIT}", status: 'SUCCESS', targetUrl: 'http://104.154.65.36:8080'
            }
     }
    }
}
