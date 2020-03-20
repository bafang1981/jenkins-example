pipeline {
        agent any
                stages {
                        stage ('One') {
                                        echo 'Hi, this is Bafang'
                        }
                }
                stage('Two') {
                         steps {
                                 input('Do you want to proceed?')
                         }
                }
                                            

        stage ('Three') {
            when {
                not {
                         branch "master"
                }
            }

            steps {
                   echo "Hello"
                
            }
            }
       
        stage ('Four') {
            parallel {
                stage('unit test') {
                                    steps {
                                          echo "running the unit test... "
                                    }
                }
                stage('integration test') {
                    agent {
                        docker {
                            reuseNode false
                            image 'ubuntu'
                        }
                    }
                    steps {
                        echo 'running the integration test ..'
                    }
                }
            }
        }
}
}
}
                   
                
             
