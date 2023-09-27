pipeline {
 agent any
   stages{
       stage('Extract_Content'){
         steps{ 
           script{
             def content = sh(script: 'cat README.txt', returnStdout: true).trim()
             env.CONTENT = content
             }
              }
       }

       stage('Send_To_Mail'){
         steps{ 
           script{
                 // Send an email with the README content from the environment variable
                    emailext(
                        subject: 'New commit',
                        body: env.CONTENT,
                        to: 'hedil.saidani@esprit.tn',
                        mimeType: 'text/plain'
                    )
           }
            }
    }

}
}
