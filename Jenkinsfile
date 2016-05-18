node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'

   // Get some code from a GitHub repository
   git url: 'https://github.com/jglick/simple-maven-project-with-tests.git'

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   def mvnHome = tool 'Maven'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "${mvnHome}/bin/mvn clean install"
   
   ansiblePlaybook credentialsId: 'e3acf4e7-93b7-44ce-9701-63cbce120125', extras: '--extra-vars warfile=$warpath', installation: 'ansible', inventory: '/home/ubuntu/hosts', playbook: '/home/ubuntu/devops/Ansible-playbooks/tomcat-buntu/site.yml', sudoUser: null

}
