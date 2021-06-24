node {

    stage('Clone repository') {
      

        checkout scm
    }
    
    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
           def customImage = app.push("node_app:${env.BUILD_NUMBER}")
            customImage.push()
        }
    }
}
