pipeline {
        agent any
        triggers {
                 pollSCM '* * * * * '
                }

        stages {
                stage (checkout){
                        steps{git 'git 'https://github.com/Rohit-457/pipeline-parameter-repo.git''}
                }
                stage (build){
                        steps{sh 'mvn install'}
                }
                stage (Deploy){
                        steps{sh 'cp target/pipeline-parameter-repo.war /home/rohit/Documents/devops/apache-tomcat-9.0.93/webapps'}
                }
        }
}

