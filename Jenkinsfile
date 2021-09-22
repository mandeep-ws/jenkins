node {
  sh "git --version"
  def datas = readYaml file: '/deploy.yml', text: "something: 'Override'"
        assert datas.something == 'Override'
}
