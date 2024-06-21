pipeline
{

    agent { 
        label 'DevServer' 
        }
    stages{
        stage('build')
        {
            steps{
                sh 'mv clean package'
            }
            post {
                success {
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }



}