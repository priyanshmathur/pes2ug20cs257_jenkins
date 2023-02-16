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
               ./opt/java/openjdk/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin/main
            }
        }
    }
    post{
      failure{
         echo "Pipline failed"
      }
    }
}
