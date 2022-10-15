pipeline
 {
    agent{ label 'kali-2'}
    environment{
                  SEC=credentials('2653d5fa-123a-47bf-ac8b-4268e751094c')
              }
    stages{
        stage('Clone')
         { steps {git branch: 'main', url: 'https://github.com/RAK5HITHM/cicd-hello-world.git' } }
        stage('Build')
         { 
            steps
            { 
               sh 'docker build -t rakshithraka/first-repo:v2 .'
            }
         } 
        stage('Push to docker Hub')
        {
         steps{
            sh 'echo $SEC_PSW | docker login -u rakshithraka --password-stdin'
            sh 'docker push rakshithraka/first-repo:v2'
         }
        }
    }          
 }
