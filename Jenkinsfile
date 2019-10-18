pipeline {
  agent any
  stages {
    stage('compilar') {
      steps {
        withMaven(globalMavenSettingsConfig: 'C:\\Users\\alumno.33\\Desktop\\Jenkins - Alumno\\maven\\conf\\settings', jdk: 'JDK', maven: 'MAVEN', mavenSettingsFilePath: 'C:\\Users\\alumno.33\\Desktop\\Jenkins - Alumno\\maven\\conf\\settings') {
          bat 'maven clean install -DskipTest'
        }

      }
    }
  }
}