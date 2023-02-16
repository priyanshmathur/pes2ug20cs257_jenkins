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
               sh 'hello_exec.cpp'
               sh 'make'
            }
        }
        stage("test"){
            steps{
               sh './hello'
            }
        }
    }
    post{
      failure{
         echo "Pipline failed"
      }
    }
}
