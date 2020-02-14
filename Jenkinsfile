
node('k8s')
{
    stage('clone the code'){
        git 'https://github.com/nagendra464/project.git'
    }
    stage('create the deployment pods'){
        sh label: '', script: 'kubectl create -f mydeploy.yml'
    }
     stage('create the sevice pods'){
        sh label: '', script: 'kubectl create -f mysvc.yml'
    }
    
    
}
