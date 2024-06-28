// pipeline {
//     agent any
//     environment {
//         Extract_URL = ""
//     }
//     stages {
//         stage('Read app.properties') {
//             steps {
//                 script {
//                     // Define the path to your app.properties file
//                     def propertiesFile = '/home/ubuntu/prime-square/application.properties'
                    
//                     // Key you want to extract
//                     def key = 'base.ui.url'
                    
//                     // Read the properties file and extract value for the key
//                     def value = sh(script: "sudo -S grep '^$key=' $propertiesFile | cut -d'=' -f2-", returnStdout: true).trim()
                    
//                     // Display the value on the Jenkins console
//                     env.Extract_URL = ${value}
//                     echo "Value for $key is: $Extract_URL"
//                 }
//             }
//         }
//     }
// }



// pipeline {
//     agent{
//         label 'built-in'
//     }
    
//     environment {
//        // Define the path to your app.properties file
//        def propertiesFile = '/home/ubuntu/prime-square/application.properties'
                    
//         // Key you want to extract
//         def key = 'base.ui.url'
//         // Initialize Extract_URL as an empty string
//         Extract_URL = sh(script: "sudo grep '^$key=' $propertiesFile | cut -d'=' -f2-", returnStdout: true).trim()
//     }
    
//     stages {
//         stage('Read app.properties') {
//             steps {
//                 script {
//                     // // Define the path to your app.properties file
//                     // def propertiesFile = '/home/ubuntu/prime-square/application.properties'
                    
//                     // // Key you want to extract
//                     // def key = 'base.ui.url'
                    
//                     // // Read the properties file and extract value for the key
//                     // value = sh(script: "sudo grep '^$key=' $propertiesFile | cut -d'=' -f2-", returnStdout: true).trim()
                    
//                     // // Assign the extracted value to Extract_URL environment variable
//                     // env.Extract_URL = value
                    
//                     // Display the value on the Jenkins console
//                     echo "Value for $key is: $env.Extract_URL"
//                 }
//             }
//         }
//     }


//      agent {
//         label 'ubuntu-server'  // Use the label assigned to the node
//     }
    
//     stages {
//         stage('Example Stage') {
//             steps {
//                 // Define your pipeline steps here
//                 sh 'echo "Hello from Node-VM2"'
//             }
//         }
//     }
// }



pipeline {
    agent {
        label 'built-in'
    }
    
    environment {
        Extract_URL = ''
        propertiesFile = '/home/ubuntu2/prime-square/application.properties'
        key = 'base.ui.url'
    }
    
    stages {
        stage('Read app.properties') {
            steps {
                script {
                    echo "Hello world from here"
                }
            }
        }
        
        stage('Example Stage') {
            agent {
                label 'ubuntu-server'
            }
            steps {
                script {
                    // Read and extract the value from application.properties
                    Extract_URL = sh(script: "sudo -S grep '^$key=' $propertiesFile | cut -d'=' -f2-", returnStdout: true).trim()
                    echo "Value for $key is: $Extract_URL"
                }
            }
        }
    }
}
