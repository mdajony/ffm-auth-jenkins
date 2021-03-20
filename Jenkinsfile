pipeline {
  agent any

  stages {
    stage('build') {
    steps {
	echo "yo..started building.."
	ls
	sh'''
	docker build -t shahedmehbubpublic/transformation-ffm-auth .
	echo "@@12345Hello" | docker login --username shahedmehbubpublic --password-stdin
	docker push shahedmehbubpublic/transformation-ffm-auth
	'''
	echo "build completed..."
    }	
   }
  }
}
