node {

stage('SCM'){
 git 'https://github.com/Nettoyjogg/gestionFerme.git'
}

stage('Compile'){
def mvnHome = tool name: 'maven-3' , type: 'maven'
sh "${mvnHome}/bin/mvn package"
}

stage('SonarQube') {
  def mvnHome = tool name: 'maven-3' , type: 'maven'
  sh "${mvnHome}/bin/mvn sonar:sonar -Dsonar.host.url=http://192.168.1.21:9000/ -Dsonar.login=“admin” -Dsonar.password=“sonar”"
    }
}
