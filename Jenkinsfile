pipeline {
  agent any
  stages {
    stage('compilar') {
      steps {
        withMaven(globalMavenSettingsConfig: 'C:\\Users\\alumno.33\\Desktop\\Jenkins - Alumno\\maven\\conf\\settings.xml', jdk: 'JDK', maven: 'MAVEN', mavenSettingsFilePath: 'C:\\Users\\alumno.33\\Desktop\\Jenkins - Alumno\\maven\\conf\\settings.xml') {
          bat 'mvn clean install -DskipTest'
        }

      }
    }
  }
}