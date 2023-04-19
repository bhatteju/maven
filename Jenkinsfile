def readxml;
node{
    stage('checking from scm'){
        checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '73348160-2876-4fbd-b2fa-cc95d7a90b32', url: 'https://github.com/bhatteju/maven.git']])
    }
    stage('readxml'){
        readxml=readMavenPom file: 'sample_java/pom.xml';
        echo "the name is : ${readxml.name}"
    }
}
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
