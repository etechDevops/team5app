pipeline{
	agent any 
	stages{
		stage('1-clone'){
			steps{
				checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-id', url: 'https://github.com/etechDevops/team5app.git']])
			}
		}
		stage('2-systemscheck'){
			steps{
				sh 'sudo systemctl status jenkins'
			}
		}
		stage('3-diskcheck'){
			steps{
				sh 'df -h'
			}
		}
		stage('4-blockcheck'){
			steps{
				sh 'lsblk'
			}
		}
        stage('5-ops-check'){
            steps{
                sh 'cat /etc/os-release'
            }
        }
        stage('6-scriptcontrol'){
            steps{
                sh 'bash -x /var/lib/jenkins/workspace/team5-job-demo/script.sh'
            }
        }
        stage('env-check'){
	        steps{
		echo "This is ${env.BUILD_NUMBER} build"
	        }
        }
	  }	
}