
pipeline {
  agent any
  tools {
    maven 'MAVEN' 
  }
parameters {
      choice(name:'respond',
      choices: 'Clean\nCompile\nTest\nInstall',
      description: 'select appropriate action')
    }

stages{
    stage('build')
        {
      steps{
          script{
            sh "mvn --version"
              sh "echo $respond"
              if ("${respond}" == "Clean")
                    {
                    sh "mvn clean"
                    }
              else if ("${respond}" == "Compile")
                    {
                    sh "mvn clean compile"
                    }
               else if ("${respond}" == "Test")
                    {
                    sh "mvn clean test"
                    }
                 else if ("${respond}" == "Install")
                    {
                    sh "mvn clean install"
                    }

}

}
 }
}
}
