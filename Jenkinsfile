pipeline
{

    agent {
        label "DevServer"
    }

    tools {
        maven 'mymaven'
    }

    stages{
        stage('build')
        {
            steps{
                sh 'mvn clean package'
            }

            post {
                success{
                    archiveArtifacts artifacts: '**/tartget/*.war'
                }
            }
        }

    }



}



// pipeline
// {

//     agent {
//      label "DevServer"
//   }
//     stages{
//         stage('build')
//         {
//             steps{
//                 echo "This is build stage"
//             }
//         }

//         stage('test')
//         {
//             steps{
//                 echo "This is test stage"
//             }
//         }
//         stage('deploy')
//         {
//             steps{
//                 echo "This is deploy stage"
//             }
//         }
//     }



// }
