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
