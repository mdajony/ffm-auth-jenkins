pipeline {
  agent any

  stages {
    stage('build') {
    steps {
	echo "yo..started building.."
	sh'''
	ls
	docker build -t shahedmehbubpublic/transformation-ffm-auth .
	echo "@@12345Hello" | docker login --username shahedmehbubpublic --password-stdin
	docker push shahedmehbubpublic/transformation-ffm-auth
	'''
	echo "build completed..."
    }	
   }
    stage('deploy') {
	steps {
	echo "starting deployment..."
	sh'''
	sshpass -p hello ssh -o StrictHostKeyChecking=no root@3.0.100.56 "docker-compose down && docker-compose pull auth && docker-compose up -d"
	'''

    }
  }

  }
}
