node {
  deleteDir()
  // Mark the code checkout 'stage'....
  stage('checkout') {
    // Checkout code from repository
    checkout scm
  }

  docker.withRegistry('https://registry.heroku.com', 'Heroku_Access_Token') {
    stage "build"
    def app = docker.build "aspdocker/web"

    stage "publish"
    app.push 'master'
  }
}