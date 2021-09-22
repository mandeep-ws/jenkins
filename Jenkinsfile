node {
  sh "git --version"
  git branch: 'main', credentialsId: 'github', url: 'https://github.com/mandeep-ws/jenkins.git'
  data = readYaml file: "deploy.yml"
  deployments = data["deployments"]
  deployments.each { e -> echo "Translating ${e.getAt('deploymentName')} - Source ${e.getAt('sourceImage')} ${e.getAt('targetImage')}"
  sh " echo ${e.getAt('sourceImage')} "}
}
