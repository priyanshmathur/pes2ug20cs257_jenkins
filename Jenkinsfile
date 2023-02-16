pipeline {
    agent any
    stages {
        stage('cloning') {
            steps {
               git branch : "main",
               url : "https://github.com/priyanshmathur/pes2ug20cs257_jenkins"
            }
        }
        stage("build"){
            steps{
               sh 'make -C main'
               echo "PATH is: ${env.PATH}"
            }
        }
        stage("test"){
            steps{
               sh "chmod +x -R ${env.WORKSPACE}"
               ./var/jenkins_home/workspace/pes2ug20cs257/main
            }
        }
    }
    post{
      failure{
         echo "Pipline failed"
      }
    }
}
