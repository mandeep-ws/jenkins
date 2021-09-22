node {
  sh "git --version"
  git branch: 'main', credentialsId: 'github', url: 'https://github.com/mandeep-ws/jenkins.git'
  data = readYaml file: "deploy.yml"
  deployments = data["deployments"]
  withCredentials([usernamePassword(credentialsId: 'github', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
  deployments.each { e -> echo "Translating ${e.getAt('deploymentName')} - Source ${e.getAt('sourceImage')} ${e.getAt('targetImage')}"
    
      sh ''' 
          echo "docker login atifactory1"
          echo " docker pull ${e.getAt('sourceImage')} "
          echo " docker tag ${e.getAt('sourceImage')} ${e.getAt('targetImage')}"
          echo " docker login atifactory2"
          echo " docker push ${e.getAt('targetImage')}"
      '''
    }
  }
}
