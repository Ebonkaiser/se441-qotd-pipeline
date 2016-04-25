stage "DEV-QA"

node {
  // all pipeline code runs on a node
  git 'https://github.com/Ebonkaiser/se441-qotd-pipeline.git'
  
  def gradleHome = tool 'Grade 2.11'
  bat "${gradleHome}\\bin\\gradle.bat assemble uploadArchives
  
  step([$class: 'ArtifactArchiver', artifacts: '**/*.war',
  fingerprint: true])
}

