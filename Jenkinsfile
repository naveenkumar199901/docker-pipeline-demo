node {
  stage('Clonning Git') {
         steps {
            
            checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'Linux@02', url: 'https://github.com/naveenkumar199901/docker-pipeline-demo.git']]]
		
			
         }
	
		}
  stage 'Docker build'
  docker.build('demo')
 
  stage 'Docker push'
  docker.withRegistry('https://324266477429.dkr.ecr.us-west-2.amazonaws.com', 'ecr:us-west-2:ECR' {
    docker.image('demo').push('latest')
  }
}
