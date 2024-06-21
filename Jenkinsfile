pipeline
{

    agent {
        label "DevServer"
    }

    parameters {
        string defaultValue: 'rishu', name: 'LASTNAME'
    }

    environment{
        NAME= "Rishu"
    }

    tools {
        maven 'mymaven'
    }

    stages{
        stage('build')
        {
            steps{
                sh 'mvn clean package'
                echo "Hello $NAME ${params.LASTNAME}"
            }

    

            stage('test')
            {
               parallel {
                stage('testA')
                {
                    steps{
                        echo "This is test A"
                    }
                }
                stage('test')
                {
                    steps{
                        echo "This is test B"
                    }
                }
               }
                post {
                success{
                    archiveArtifacts artifacts: '**/target/*.war'
                }
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
