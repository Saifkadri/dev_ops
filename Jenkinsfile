pipeline {
      agent any
          stages {

	        stage('Checkout GIT ') {
                 steps {
                    echo 'Pulliing ...';
			 git branch: 'Youssef', credentialsId: 'Git', url: 'https://github.com/Saifkadri/dev_ops.git'
		           
                        }
                 }
}
}
