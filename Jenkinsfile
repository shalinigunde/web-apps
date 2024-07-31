pipeline { 
    agent any
      stages {
        stage("Build") {
            steps {
                echo "Building branch ${env.Dev}..."
            }
        }
        stage ('notification') {
            steps{
                echo 'deployment started'
            }
        }  
        stage ('install nginx') {
            steps{
                sh 'sudo apt install nginx -y'
            }
        }
        stage ('Delete default page') {
            steps{
                sh 'sudo rm -rf /var/www/html/*'
            }
        }
        stage ('copy to web server') {
            steps{
                sh 'sudo cp -rf /var/lib/jenkins/workspace/Job-1/* /var/www/html/'
            }
        }
        stage ('update nginx') {
            steps{
                sh 'sudo systemctl restart nginx'
            }
        }
        stage("Deploy") {
            steps {
                echo "Deploying branch ${env.Dev}..."
            }
        }
        stage ('sucess') {
            steps{
                echo 'deployment success'
            }
        }
        stage ('If failure') {
            steps{
                echo 'deployment failure'
            }
        }
    }
}
