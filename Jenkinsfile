pipeline {
    agent any

    stages {
        
        stage('OX Security Scan') {
            agent {
                docker {
                    alwaysPull true
                    image 'oxsecurity/ox-block-mode:latest'
                }
            }
            environment {
                OX_API_KEY = credentials("OX_API_KEY")
	            NODE_TLS_REJECT_UNAUTHORIZED = 0
		        // JENKINS_HOME=true
	            // BUILD_NUMBER='7' 
		        // BUILD_URL='B'
		        // OX_HOST_URL='https://app.ox.security'
	            // GIT_URL='https://github.com/michaelhorty/vulpy'
		        // GIT_COMMIT='19d065c25d8fd2169391e187ed6ee8b9f98750eb'
		        // GIT_BRANCH='origin/main'
                // OX_TIMEOUT = 20
                // OX_FAIL_ON_TIMEOUT = false
                // OX_FAIL_ON_ERROR = false
            }
            steps {
                script {
                    sh 'ox-block-mode'
                }
            }
        }
    }
}

