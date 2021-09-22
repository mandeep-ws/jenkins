node {
  sh "git --version"
  data = readYaml file: "./deploy.yml
  deployments = data[deployments]
  deployments.each { e ->
                echo "Translating ${e.getAt('deploymentName')} deploymentName 
    ${e.getAt('sourceImage')} ${e.getAt('targetImage')}"
}
}
