pipeline {
  agent any
    stages {
        stage("Build") {
            steps {
                echo "Building branch ${env.main}..."
                echo "build is completed"
            }
        }
      stage("Deploy") {
            steps {
                echo "Deploying branch ${env.main}..."
            }
        }
    }  
}
