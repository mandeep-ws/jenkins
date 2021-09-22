node {
  sh "git --version"
  data = readYaml file: "Jenkins/config.yml
  scan_path = data[scan_path]
  scan_path.each { e ->
                echo "Translating ${e.getAt('application')} application 
${e.getAt('path')}"
}
}
