

pipeline {
    agent {   
            node { label 'docker' } 
      }
     options {
        buildDiscarder(logRotator(numToKeepStr: '5', daysToKeepStr: '14'))
        timestamps()
    }
    environment {
        AWS_ACCESS_KEY = credentials('AWS_ACCESS_KEY')
        AWS_SECRET_KEY = credentials('AWS_SECRET_KEY')
    }
    parameters { 
       string(name: 'ECR_REPO', defaultValue: 'api', description: 'Please enter the ecr repo name')
       string(name: 'ECR_URL', defaultValue: '285965978269.dkr.ecr.eu-west-1.amazonaws.com', description: 'Please enter the ecr url')
       
    }
    stages {


        stage('BUILD & UNIT TESTING') {
         parallel {
            stage('API') {
                steps {
                    sh  '''
                        node --version
                    '''
                }
             }
           stage('WEBAPP') {
                steps {
                    sh  '''
                        node --version
                    '''
                }
             }
           }
        }
        stage('CODE_ANALYSIS') {
         parallel {
            stage('API') {
                steps {
                    sh  '''
                        node --version
                    '''
                }
             }
           stage('WEBAPP') {
                steps {
                    sh  '''
                        node --version
                    '''
                }
             }
           }
        }
        stage('QUALITY_GATE') {
         parallel {
            stage('API') {
                steps {
                    sh  '''
                        node --version
                    '''
                }
             }
           stage('WEBAPP') {
                steps {
                    sh  '''
                        node --version
                    '''
                }
             }
           }
        }
        stage('BUILD_IMAGE') {
         parallel {
            stage('API') {
                steps {
                    sh  '''
                        node --version
                    '''
                }
             }
           stage('WEBAPP') {
                steps {
                    sh  '''
                        node --version
                    '''
                }
             }
           }
        }
        stage('PUSH_IMAGE') {
         parallel {
            stage('API') {
                steps {
                    sh  '''
                        node --version
                    '''
                }
             }
           stage('WEBAPP') {
                steps {
                    sh  '''
                        node --version
                    '''
                }
             }
           }
        }
        stage('DEPLOY_DEV') {
             steps {
                    sh  '''
                        node --version
                    '''
                }
         }
         stage('OWASP_TESTING') {
             steps {
                    sh  '''
                        node --version
                    '''
                }
         }
         stage('INTEGRATION_TESTING') {
             steps {
                    sh  '''
                        node --version
                    '''
                }
         }
         stage("Ready to deploy on QA ?") {
           steps {
               script {
						 input(message: 'Do you want to continue?', ok: 'Continue')
               }		    
					
           }
        }
        stage("DEPLOY_QA") {
           steps {
               sh  '''
                        node --version
                '''		    
					
           }
        }
        stage("FUNCTIONAL_TESTING") {
           steps {
               sh  '''
                        node --version
                '''			    
					
           }
        }
        stage("Ready to deploy on Perf ?") {
           steps {
               script {
						 input(message: 'Do you want to continue?', ok: 'Continue')
               }		    
					
           }
        }
        stage("DEPLOY_PERF") {
           steps {
               sh  '''
                        node --version
                '''			    
					
           }
        }
        stage("PERF_TESTING") {
           steps {
               sh  '''
                        node --version
                '''			    
					
           }
        }
        stage("Ready to deploy on LIVE ?") {
           steps {
               script {
						 input(message: 'Do you want to continue?', ok: 'Continue')
               }		    
					
           }
        }
        stage("DEPLOY_LIVE") {
           steps {
               sh  '''
                        node --version
                '''			    
					
           }
        }


        
         
    }
}
