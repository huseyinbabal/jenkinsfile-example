node {
    def app

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("huseyinbabal/jenkinsfile-example")
    }

    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'hub') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
