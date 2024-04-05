node {

    stage("Git Clone"){
        git branch: 'main', url: 'https://github.com/ArsalanSan/dp-app.git'
    }
    
    withCredentials([string(credentialsId: 'DOCKER_HUB_TOKEN', variable: 'TOKEN')]) {
        sh "docker login -u arsalansan -p $TOKEN"
    }
    
    stage("Docker build"){
        sh "docker build -t arsalansan/dp-app:latest ."
    }

    stage("Push Image to Docker Hub"){
        sh "docker push  arsalansan/dp-app:latest"
    }

}
