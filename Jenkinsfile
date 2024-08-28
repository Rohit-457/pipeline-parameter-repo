pipeline {
        agent any
        triggers {
                 pollSCM '* * * * * '
                }
	parameters {
 		 choice choices: ['QA', 'UAT'], description: 'choose the server', name: 'ENVIRONMENT'
		}	
	parameters {
 		 string description: 'type  the server name ', name: 'ENVIRONMENT'
		}
        stages {
                stage (checkout){
                        steps{git 'https://github.com/Rohit-457/pipeline-parameter-repo.git'}
                }
                stage (build){
                        steps{sh 'mvn install'}
                }
                stage (Deploy){
                        steps{sh '''if [ $ENVIRONMENT = "QA" ];then
	cp target/pipeline-parameter-repo.war /home/rohit/Documents/devops/apache-tomcat-9.0.93/webapps
			elif  [ $ENVIRONMENT = "UAT" ];then
         cp target/pipeline-parameter-repo.war /home/rohit/Documents/devops/apache-tomcat-9.0.93/webapps
			echo "deployment has been done!"
			fi'''
			}
                }
        }
}
