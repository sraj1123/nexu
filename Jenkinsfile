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



pipeline {
    agent any
    
    environment {
        // Initialize Extract_URL as an empty string
        Extract_URL = ""
    }
    
    stages {
        stage('Read app.properties') {
            steps {
                script {
                    // Define the path to your app.properties file
                    def propertiesFile = '/home/ubuntu/prime-square/application.properties'
                    
                    // Key you want to extract
                    def key = 'base.ui.url'
                    
                    // Read the properties file and extract value for the key
                    value = sh(script: "sudo grep '^$key=' $propertiesFile | cut -d'=' -f2-", returnStdout: true).trim()
                    
                    // Assign the extracted value to Extract_URL environment variable
                    env.Extract_URL = value
                    
                    // Display the value on the Jenkins console
                    echo "Value for $key is: $env.Extract_URL"
                }
            }
        }
    }
}
