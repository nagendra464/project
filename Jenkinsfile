
node('k8s')
{
    stage('login to nag'){
        sh label: '', script: 'cd /home/nag'
    }
    stage('clone the code'){
        git 'https://github.com/nagendra464/project.git'
    }
    stage('create the deployment pods'){
        sh label: '', script: 'kubectl create -f mydeploy.yml'
    }

    
    
}
