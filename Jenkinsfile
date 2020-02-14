
node('Docker'){
    

    stage('Clone the code') {
        
        git 'https://github.com/nagendra464/project.git'
       
    }
     stage('mvn goals') {
        
        sh label: '', script: 'mvn clean install package'
       
    }
    
    stage('Build image') {
       

        sh label: '', script: 'docker build -t nagendra464/naglogin:1 .'
    }
    stage('Push image') {
        withCredentials([string(credentialsId: 'dockerpwd', variable: 'dockerpwd')]) {
            sh label: '', script: "docker login -u nagendra464 -p ${dockerpwd}"
    }
        
        sh label: '', script: 'docker push nagendra464/naglogin:1'
    }

    stage('create container'){
        sh label: '', script: 'docker run --name testlogin -d -p 80:8080 nagendra464/naglogin:1'   
        
    }
    
}
node('k8s')
{
    stage('clone the code'){
        git 'https://github.com/nagendra464/project.git'
    }
    stage('create the deployment pods'){
        sh label: '', script: 'kubectl apply -f mydeploy.yml'
    }
     stage('create the sevice pods'){
        sh label: '', script: 'kubectl apply -f mysvc.yml'
    }
    
    
}
