node() {
    stage "Checkout"

    checkout scm

    stage "Docker Build & Push"

    sh "docker build -t graviteeio/website:v2 --pull=true ."
    sh "docker container stop beta"
    sh "docker container rm beta"
    sh "docker container run -d --rm --name beta graviteeio/website:v2"
}
