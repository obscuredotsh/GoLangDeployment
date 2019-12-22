pipeline {
	agent any
	parameters {
  text defaultValue: '', description: '', name: 'IPs'
}
	stages {
	stage ('Ansible/CiCd - Checkout') {
	steps {
	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/prateerickaien/GoLangDeployment.git']]]) 
	}
	}
	stage ('Ansible/CiCd - Build') {
	steps {
			// Shell build step
sh ''' 
#cp -r /ci-cd/* . 

cp hello.go roles/cicd/files/hello.go
'''
	}
	}
	stage ('Deploying New Code') {
	steps {
sh '''
for items in $IPs
do

echo "$items ansible_python_interpreter=/usr/bin/python3 ansible_ssh_user=ubuntu ansible_ssh_private_key_file=/home/ubuntu/pemfile/test.pem ansible_ssh_common_args='-o StrictHostKeyChecking=no'" >> hosts
done

ansible-playbook playbook.yml -i hosts -vv 
'''
}
}
}
	}

