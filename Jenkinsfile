pipeline{
    
    agent any
    
    tools{
        maven 'mymaven'
    }
    
    stages{
        stage('Clone Repo')
        {
            steps{
                git ' https://github.com/vivekkb-code/star-agile-insurance-project.git '
            }
        }
        stage('Test Code')
        {
            steps{
                sh 'mvn test'
            }
        }
        
        stage('Build Code')
        {
            steps{
                sh 'mvn package'
            }
        }
        stage('Build Image')
        {
            steps{
                sh 'docker build -t myinsuranceproject:$BUILD_NUMBER .'
            }
        }
        
        stage('Deploy the Image')
        {
            steps{
                sh 'docker run -d -P myinsuranceproject:$BUILD_NUMBER '
            }
        }
    }
}




