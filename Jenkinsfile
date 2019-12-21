
node
{
    stage('clone the code'){
        git 'https://github.com/nagendra464/project.git'
    }
    stage('maven roles'){
        sh label: '', script: 'mvn install'
    }
    stage('the end'){
        sh label: '', script: 'echo "the end"'
    }
   stage('new project'){
       sh label: '', script: 'echo "the new file is added"'
   } 
    satge('new file'){
        sh label: '', script: 'echo "the new file is added"'
    }
}
